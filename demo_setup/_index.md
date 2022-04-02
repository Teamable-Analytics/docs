# Demo Preparation & Execution

## Definitions
**Canvas:**
*The production or "real" Canvas.*

**CanvasTest:**
*The testing environment for Canvas. It contains a dump of the real Canvas database that is updated monthly.*

**Teamable Analytics Verf:**
*The staging version of Teamable Analytics, accessible through CanvasTest. We refer to this as `ta-verf`.*

**Teamable Analytics Prod:**
*The live production build of Teamable Analytics, accessible through Canvas. We refer to this as `ta-prod`.*

> Note: We denote Teamable Analytics as `TA` in further documentation

## High-level setup
Before the process begins, the prerequisites are:
- A course with `TA` implemented. (This needs to be done by CTLT)
    - This course needs to have students (test Canvas users)
    - Ideally the course also has sections with students divided evenly among them.
- The impending threat of a demo on your back 👀.

After that is complete, the steps are as follows:
1. Consolidate changes.
2. Deploy changes and ensure stability.
3. Data setup.
4. Test run.
5. Complete demo.

### Step 1: Consolidate Changes
Any changes needed for the demo will need to be completed and merged to the `master` branch.
It goes without saying that these should be tested and validated to avoid complications during
the demo.

Specifically, the current process is (a) merge to `master`, (b) deploy to `ta-verf`, then (c) deploy to the `ta-prod`.

Currently, only CTLT members can deploy to `ta-verf`/`ta-prod`.

### Step 2: Deploy changes and ensure stability.
1. Ensure `ta-verf` is stable and running.
2. Ensure CanvasTest is connected to `ta-verf`.
   > Whenever CanvasTest refreshes data from Canvas, the connections to `TA` are broken. 
   Since Canvas connects to `ta-prod`, when the refresh happens, CanvasTest will now try to connect to `ta-prod`. This 
   isn't allowed so usually the links from CanvasTest to `TA` will just disappear entirely. This needs to be manually
   reconnected by a CTLT member.
   > 
   > You can tell this is the problem if links to `TA` from courses it is implemented in do not work or are not there.
3. Ensure connections are working.
   > Sometimes after reconnecting CanvasTest to `ta-verf`, opening the app and using features that integrate with the 
   > Canvas API (importing, pulling, pushing) will cause errors. This is another problem solved by CTLT.

### Step 3: Data setup.
Now we're ready to set up the data. There are a few types:
- Student data
- Assignment data
- Survey data
- Peer evaluation data

#### Student Data
The student data comes from Canvas/CanvasTest and is completed by clicking the "Import Course Data" button in 
`<COURSE_ID>/sections`. As long as the data exists in the connected Canvas instance, this will work 
(CanvasTest for `ta-verf` and Canvas for `ta-prod`). 

Remember that CanvasTest refreshes with the data from Canvas monthly on pre-assigned dates that CTLT will know (so we 
can plan in advance), but this refresh cannot be manually triggered.

> Note: Student accounts cannot log in to CanvasTest at all. So peer evaluations and surveys cannot be mock-completed in
> CanvasTest/`ta-verf`.

#### Assignment Data
In order to demonstrate the "Monitor Teams" functionality, assignment grades are needed. This means creating
assignments/quizzes in CanvasTest and giving each student a grade in the gradebook for them.

The easiest way I could do this was to make a "Graded Quiz" with 1 question that's an "essay question". You can set any
number of total marks for an essay question, so choose a number that makes sense. Then go to the gradebook and give each
student a mark. (To be extra thorough, I generated a set of normally distributed integers of the class size)

#### Survey Data

#### Peer Evaluation Data

### Step 4: Test run.


### Step 5: Complete demo.