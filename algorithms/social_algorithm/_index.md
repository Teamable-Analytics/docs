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

## Pseudocode

Before the algorithm begins, we define a sequence of constants:
`max_team_size`
`min_team_size`
`num_teams`
`max_num_friends`
`max_num_enemies`

### Inputs

At a base level, the social algorithm requires the social preferences for all students within a course. If students were
permitted to specify project preferences in the survey associated with the team generation, then these preferences are
also considered.

Before the algorithm begins, the social preferences of all students are compiled into a directed graph with FRIEND and
ENEMY edges.

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

Also, the fragments of size 1 are ignored, even if it means leaving empty team slots.

### Stage 3: Merging Clique Fragments

Next, the algorithm aims to fill the team slots currently containing fragments.
This process is fairly simple:
1. Find the largest fragment-containing team (i.e. a team with less than `min_team_size` members at this stage).
2. 

### Stage 4: Place Remaining Students

### Stage 5: Assigning Projects

## Scoring

## Drawbacks

### Time Constraints

