# 6. Requirements specification

## 6.1 Approach

- Requirements are derived from the project proposal (Section 1), the literature review (Section 3), the comparison of existing systems (Section 4) and the identified risks (Section 10.5).
- **Priority** (MoSCoW): Must = required for the prototype; Should = important, can be dropped under time pressure; Could = optional.
- **Stage:** P1 = prototype for pre-defense 1; P2 = planned for pre-defense 2.
- **Source** shows where the requirement comes from. "Assumption" means it is not yet confirmed by interviews (Section 2) and is treated as unverified.
- Every requirement has an acceptance criterion that can be checked by a test, a demonstration or an inspection.

## 6.2 Functional requirements

| ID | Requirement | Priority | Stage | Acceptance criterion | Source |
|---|---|---|---|---|---|
| FR-1 | The user can choose a procedure (CPR or blood draw) in a menu at application start | Must | P1 | The menu lists both procedures; selecting one starts the corresponding scenario without restarting the application | Proposal 1.6 |
| FR-2 | The system guides the user step by step through the procedure | Must | P1 | For every step in the procedure definition, an instruction is shown when the step becomes active (checked by walking through all steps of both procedures) | Proposal 1.4 (obj. 6) |
| FR-3 | The system checks whether each step was performed correctly and in the correct order | Must | P1 | In a scripted correct run all steps are accepted; in at least one scripted incorrect run (wrong action or wrong order) the step is not accepted | Proposal 1.4 (obj. 6, 7) |
| FR-4 | The system gives immediate feedback on correct and incorrect actions | Must | P1 | Visual or audio feedback appears within 1 second after the action (measured in a test run) | Proposal 1.4 (obj. 6); Lit. review [6] |
| FR-5 | CPR scenario: the system measures compression rate and counts compressions and compares them with guideline values | Must | P1 | (a) Measurement accuracy: in a test session of at least 30 compressions, the measured count equals the reference count and the measured rate is within ±5 compressions/min of the reference timing. (b) Guideline check: the system shows whether the user's rate is inside the AHA/ERC range (100–120/min) | Proposal 1.4 (obj. 7); Lit. review [6] |
| FR-6 | CPR scenario: the system estimates compression depth from the input method | Should | P1 | Depth is displayed and compared with the guideline range, or the limitation of the input device is documented; if displayed, depth is also recorded (see FR-9) | Assumption; Lit. review [1], [6] |
| FR-7 | Blood draw scenario: the system tracks the sequence of procedure steps defined from a published guideline | Must | P1 | All steps of the blood draw checklist are implemented and traceable to the guideline (see NFR-5) | Proposal 1.6 |
| FR-8 | The system uses a scoring rule for each step defined in the procedure definition | Must | P1 | Each step has a rule (at least pass/fail); the session score is computed from these rules and matches a manual calculation for a recorded session | Proposal 1.6; Risk R5 |
| FR-9 | The system collects performance data during a session (time per step, step correctness; for CPR also compression rate and count) | Must | P1 | After a session, the recorded data contains time and result for every step; for the CPR scenario it also contains rate and count | Proposal 1.4 (obj. 7); Lit. review [3], [13] |
| FR-10 | At the end of a session the system shows a results summary (total time, completed, missed and incorrect steps, score) | Must | P1 | The summary is shown after both procedures and matches the recorded data | Proposal 1.5 |
| FR-11 | New procedures are added through a procedure module (steps, conditions, metrics, scoring rules) without changes to the core system | Must | P1 | The second procedure (blood draw) is added through the module; the Git diff shows no changes to core code | Proposal 1.4 (obj. 4, 8); Lit. review [9], [13] |
| FR-12 | The user can repeat a procedure and return to the menu after a session | Should | P1 | After the summary, the user can restart the same procedure or return to the menu | Proposal 1.1 (repeated practice) |
| FR-13 | User roles: trainee, instructor, administrator | Should | P2 | Different roles see different functions after login | Proposal 1.2, 1.6 |
| FR-14 | Persistent storage of session results and progress tracking | Should | P2 | Results of a session are available after the application is restarted | Proposal 1.6 |
| FR-15 | Instructor view for reviewing trainee results | Should | P2 | An instructor can open the list of sessions of a trainee and see their summaries | Proposal 1.2, 1.6 |

## 6.3 Non-functional requirements

| ID | Category | Requirement | Priority | Stage | Acceptance criterion | Source |
|---|---|---|---|---|---|---|
| NFR-1 | Performance | The application runs at a stable frame rate on the target headset | Must | P1 | Average frame rate is at least 90% of the headset's native refresh rate during a 5-minute session (profiler), with no drop below that level longer than 1 second | Risk R2; Lit. review [3] |
| NFR-2 | Compatibility | The prototype runs as an application on the selected headset with fixed Unity and XR package versions | Must | P1 | The built application starts and both procedures can be completed on the target device | Risks R4, R7; Lit. review [2] |
| NFR-3 | Usability | A new user can start and complete a procedure after a short introduction (smoke usability check, not a statistical evaluation) | Should | P1 | 3 or more test users complete a procedure after at most 2 minutes of instruction; the SUS score is reported as indicative only | Assumption; Lit. review [11] |
| NFR-4 | Comfort | The application does not move the user's view without the user's action (no forced locomotion) | Should | P1 | Inspection of both scenarios confirms no artificial camera movement | Assumption; Lit. review [11] |
| NFR-5 | Medical accuracy | Every procedure step is traceable to a published clinical guideline | Must | P1 | Each step in the procedure definition has a guideline reference; unvalidated steps are marked as such | Risks R1, R3 |
| NFR-6 | Privacy | The prototype does not collect personal data; results are stored only locally or anonymised | Must | P1 | Inspection of stored data shows no personal identifiers | Risk R8 |
| NFR-7 | Reliability | A full session completes without crashes | Should | P1 | 10 consecutive full sessions per procedure without crash | Assumption |
| NFR-8 | Extensibility | The procedure definition format is documented so that a new procedure can be described without reading core code | Should | P1 | The format is described in the documentation (Section 7) and was used for the second procedure | Proposal 1.4 (obj. 4) |
| NFR-9 | Comfort | A single session does not exceed 15 minutes | Could | P1 | Measured duration of a full run of each procedure is at most 15 minutes | Assumption; Lit. review [11] |

## 6.4 Out of scope

Requirements for additional procedures, clinical validation with real patients, support for all AR/VR devices and integration with learning management systems are out of scope (see Section 1.6).
