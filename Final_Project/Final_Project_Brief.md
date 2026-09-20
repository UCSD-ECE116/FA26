# Final project: model-gated embedded application

Build an individual application in which a new model runs on the XIAO ESP32-S3 Sense, a
policy interprets its predictions, and an accepted event produces a useful end-action.
Choose the application and implementation. You may use pretrained or student-trained models,
external libraries, and AI coding support. Training from scratch is not required.

The final project contributes **25 percent** of your course grade. A1-A4 each contribute
18.75 percent. There is no project proposal or final oral examination.

## Schedule

The brief is available from the start of the quarter. The project introduction is November 17.
Dedicated project implementation begins after A4 is due November 20. November 24, December 1,
and December 3 are supported project work sessions. There is no November 26 class.

Submit both deliverables to the final-project Canvas assignment by **Friday, December 4,
2026, at 7 p.m. Pacific**. Automatic grace runs through 11:59 p.m. Friday. Submissions from
Saturday midnight receive one 25-percent deduction from the earned score. Canvas closes
Monday, December 7, at 7 p.m. Approved accommodations and emergencies follow the course policy.
There is no required project submission before the final deadline.

## Required system

1. **New on-device model.** Use a model for a task different from the required A2 voice-command
   and A3-A4 hand-gesture tasks. Identify the model source/version, labels or output meaning,
   input shape, preprocessing, and deployment toolchain. Actual inference must run on the XIAO
   using relevant sensor input. You may reuse earlier acquisition, deployment, and measurement
   infrastructure. Changing only the threshold of a supplied course model does not satisfy this
   requirement. A host computer may support the end-action but cannot replace local inference.
2. **Model characterization.** Evaluate the deployed model under documented conditions using
   examples separate from those used to choose its settings. Include target and non-target
   conditions, report counts and task-appropriate errors/metrics, and identify limitations.
   Measure inference latency on the device and report model size and memory use, distinguishing
   physical measurements from compiler/profiler reports. Explain the input/output contract.
3. **Decision gate.** State exactly when the system permits or suppresses an action. Specify
   decision thresholds or equivalent logic, any temporal confirmation, repeat suppression,
   and re-arming. Explain false-activation and missed-event consequences. Compare at least two
   policy settings using the same evaluation conditions and justify your final choice.
4. **Useful end-action.** An accepted event must change a physical or software application:
   operate an actuator, request processing, control an interface, save a useful recording,
   change sensing mode, or another purposeful action. Displaying a model score or printing a
   prediction alone is diagnostic output and does not satisfy the end-action requirement.
5. **End-to-end evidence.** Test intended activation, correct non-activation, sustained or
   repeated input, and a relevant failure followed by recovery. Distinguish model errors from
   gate and integration errors. Measure event-to-action delay and report false activations,
   missed actions, and successful actions with their denominators.
6. **Bounded operation.** Define the safe/default state and recovery behavior appropriate to
   your action. Document what data leaves the device and where it is stored. Keep credentials
   out of firmware, shared files, and submitted evidence. Networked projects must handle
   disconnection or timeout; local projects must test a relevant local failure. Generated
   service output must pass deterministic checks before it controls a physical action.

Use at least **20 target trials and 20 non-target trials** for the final gate evaluation, spread
across at least two documented operating conditions. Also test sustained/repeated input and one
failure/recovery case. Ordered trials must represent separate event opportunities; adjacent
frames from one held input are not independent trials. These are minimum reporting requirements,
not evidence that the system generalizes broadly. Use additional data where your claims require
it. Choose task-appropriate model metrics and explain the evaluation unit.

No common accuracy threshold applies to all projects. Scope, honest diagnosis, evidence quality,
and justified decisions matter. Expensive hardware, paid services, model size, or interface
polish do not earn extra credit by themselves. A local application using the existing kit can
satisfy the requirements. Any added components must be compatible with the hardware and powered
appropriately; do not connect course hardware to mains voltage.

## Deliverables

Submit **two files together in one Canvas submission**:

- `Final_Project_<student-id>.pdf`: a four-page report, including figures, tables, references,
  and assistance disclosure. Use readable type of at least 10 points. Do not add a cover page
  or required appendix beyond the four pages.
- `Final_Project_<student-id>.mp4`: a 3-5 minute video. Show the real device, relevant input,
  gate behavior, and end-action. Include a successful action, a rejected/non-target condition,
  repeated-input behavior, and the failure/recovery case. Explain the architecture and one
  evidence-based design choice. Captions or on-screen text must convey essential narration.

No separate source-code archive, public repository, proposal, or oral defense is required.
Include the model identifier, key configuration values, test conditions, sample counts, and
results in the report so the claims are traceable. Do not put credentials or private recordings
in either deliverable. Download/open both uploaded files to verify the submission. If you
resubmit, include both files again; staff grade the latest eligible complete submission.

A useful report organization is: (1) application and architecture, (2) model characterization,
(3) gate and integration decisions, and (4) system results, limitations, and attribution.
You may organize the four pages differently if all required evidence remains clear.

## Coding support and attribution

You are encouraged to use coding assistants and other implementation support, including code
generation, libraries, debugging, and refactoring. Name substantive tools and sources, describe
what they contributed, and explain what you tested or changed. You remain responsible for the
system and its explanation. Collect your own measurements and demonstrate your own hardware.
Do not fabricate results, submit another student's project, or claim generated evidence as an
observation. Report incomplete behavior honestly.

## Rubric

| Criterion | Points | Full-credit evidence |
|---|---:|---|
| Model deployment and characterization | 30 | New qualifying model runs on the device; provenance, input/output contract, fair evaluation, device timing, resource reports, and limitations are documented |
| Gate design and justification | 25 | Explicit activation/suppression/re-arm behavior; controlled comparison supports the selected policy; false activations and misses are interpreted |
| End-action and system evaluation | 25 | Working useful action follows the local gate; required trials and end-to-end timing distinguish model, gate, and integration behavior |
| Failure behavior and limitations | 10 | Relevant failure/recovery test, bounded behavior, and applicable data/credential safeguards match observed operation |
| Communication and attribution | 10 | Video and four-page report are readable, consistent, traceable, and disclose sources and substantive coding assistance |
| Total | 100 | |

For each criterion, complete and well-supported evidence earns 90-100 percent of its points;
substantially correct work with limited gaps earns 70-89 percent; partial implementation with
useful diagnostic evidence earns 40-69 percent; minimal relevant evidence earns 1-39 percent;
absent evidence earns zero. Apply these bands to the demonstrated portion of each criterion.
A missing on-device model cannot receive deployment credit, and an absent end-action cannot
receive working-integration credit. Strong presentation cannot replace missing technical work.

## Optional project directions

See [project direction modules](Project_Directions.md). These offer application ideas and design
questions. You may choose another direction that satisfies the common requirements. They have
no separate submission or quiz and are not step-by-step project solutions.
