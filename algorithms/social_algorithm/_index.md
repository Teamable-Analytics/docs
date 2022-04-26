# Social Algorithm

## Overview

This algorithm aims to focus solely on the social connections between students and forming teams based on these
connections. We also aim to reward student self-organization, so students who set up their preferences in such a way
that everyone indicates a preference for other team members are given their desired team composition. Furthermore, more
organized teams are more likely to be assigned to the project that most of their members indicated a preference for.

### Definitions

*Clique* - A complete sub-graph of the overall relationship
*Team Slot* -
*Fragment* -
*Available Team* - 

### Inputs

At a base level, the social algorithm requires the social preferences for all students within a course. If students were
permitted to specify project preferences in the survey associated with the team generation, then these preferences are
also considered.

Before the algorithm begins, the social preferences of all students are compiled into a directed graph with FRIEND and
ENEMY edges.

## Pseudocode

Before the algorithm begins, we define a sequence of constants:
`max_team_size`
`min_team_size`
`num_teams`
`max_num_friends`
`max_num_enemies`

### Stage 1: Finding Student Cliques

The first stage of the algorithm finds cliques of students that contain `max_team_size` students.

We then "clean" these cliques, which simply means that only cliques with unique sets of students are included. In this
process, the clique that is discovered first will be given priority.
> e.g. if two cliques [A. B, C] and [B, C, D] are found in that order, then after cleaning this set of cliques, only [A, B, C] will remain.

For each clean clique, we place it into the next empty team slot. As an additional step, we lock these teams so that
they remain unchanged for the est of the process.

### Stage 2: Finding Clique Fragments

The next stage deals with all cliques that contain a number of students that is ≤ `min_team_size`. We refer to cliques
of this size as "*fragments*". These fragments are not "cleaned" as described in Stage 1. Even so, a clique will not be
considered if one or more of its members have already been assigned to teams by the team is is being processed.

At a high level, this stage fills remaining team slots with fragments, considering larger fragments before smaller ones.

For each group of fragments with size `f`, we actually place them into empty team slots in order of their
team_suitability_score() (i.e. a fragment with a higher team_suitability_score will be placed into an empty team slot
before a fragment of the same size with a lower team_suitability_score). This does very little when generating teams,
and is only done to support future improvements to facilitate team regeneration using this algorithm. See, when
regenerating teams with peer evaluation data, we'll need to lower the threshold of the [social graph](./social-graph.md)
, meaning that a clique will not necessarily imply a group of students where everyone is explicitly friends with
everyone else, so fragments of the same size are not all the same thing. This is also the reason cliques in this stage
are not cleaned, so that between two cliques containing overlapping members, the better __scoring__ clique is chosen.

Fragments that are exactly the `min_team_size` are also locked to prevent further modification. This is done so no extra
students are not added to organize steams of the minimum team size, either.

__Clause 2.I:__ The fragments of size 1 are ignored, even if it means leaving empty team slots.

### Stage 3: Merging Clique Fragments

Next, the algorithm aims to fill the team slots currently containing fragments. This process is fairly simple:

1. Find the largest fragment-containing team (i.e. a team with less than `min_team_size` members at this stage).
2. Find cliques of size `fill_size` and smaller where `fill_size`=`min_team_size`-(size of fragment).
   > All cliques `fill_size` and smaller are considered, but cliques of size 1 are only considered if only cliques of size 1 are present. If larger cliques are available, that will be favoured.
3. Add the clique best suited to join the team (as determined by team_suitability_score) to the team.
4. Repeat Step 3 until the team has `min_team_size` members.
5. Repeat Steps 1-4 until there are no longer any fragment teams.

Note that this process will also fill any empty team slots that still exist due to Clause 2.I.

### Stage 4: Place Remaining Students

Stage 4 places any unassigned students into available teams. 

### Stage 5: Assigning Projects

## Scoring

## Limitations

### Unassigned Students

It is technically possible for students to remain unassigned by the end of this algorithms run. Imagine a class of 10
students, where you wish to create 3 teams (`num_teams=3`). This sets `min_team_size=3` and `max_team_size=4`. If there
exist 3 cliques of size 3 (i.e. [A, B, C], [D, E, F], and [G, H, I]) within the class, then they will be found and these
teams will be locked in Stage 2. The 10th student (Student J) would remain outside of a team in this case. Naturally,
this case is unlikely, but it does remain a possibility.

### Group Splitting

This occurs when "almost-cliques" exist. Say 5 friends [A, B, C, D, E] tried to organize to all be friends. For some
reason, Student A forgot to write Student D as a preference and Student B forgot to write Student E as a preference.
Because of the way clique cleaning works, it will identify [A, B, C] and [D, E] as separate fragments. If these
fragments both so happen to be selected to fill empty team slots (i.e. they are the largest), it is now impossible for a
team [A, B, C, D, E] to exist. The algorithm never even performs the comparison required to know that the
fragment [D, E] would fit in really well with the fragment [A, B, C].

### Time Constraints

