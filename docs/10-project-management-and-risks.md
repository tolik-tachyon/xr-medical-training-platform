# 10. Project management and risks

## 10.1 Git repository

* Repository: https://github.com/tolik-tachyon/xr-medical-training-platform.git
* Structure:
  * `prototype/` — Unity project
  * `docs/` — documentation and pre-defense materials
  * `README.md`
  * `.gitignore` — Unity template
* Every change is linked to a YouTrack task: the task ID is included in the branch name and in the commit or pull request description.
* Branch example: `XMT-16-Project-Management-And-Risks`
* Commit example: `XMT-2: add project proposal content`
* Changes are merged through pull requests; the PR description lists the related YouTrack tasks.

### Traceability example

| Deliverable | YouTrack task | Branch / commit |
|---|---|---|
| Project proposal | XMT-2 | commit `XMT-2: add project proposal content` |
| Project management and risks | XMT-16 | branch `XMT-16-Project-Management-And-Risks` |
| README | XMT-15 | commit `XMT-15: prepare README` |
| Git repository setup | XMT-4 | commit `XMT-4: set up repository structure` |

## 10.2 YouTrack project

* Project and board: https://xr-medical-training-platform.youtrack.cloud/agiles/204-1/current
* Board columns: Backlog, Develop, Review, Test, Staging, Done.
* A task is created for each meaningful work item. Each task has an assignee, expected outcome, acceptance criteria, and deadline.
* A link to the relevant commit or pull request is added to the task.
* A task is moved to Done only when its acceptance criteria are met.
* The repository and the board are accessible to the supervisor and the committee.

## 10.3 Allocation of responsibilities

| Role | Name | Responsibilities |
|---|---|---|
| Student | Anatoliy Tsoy | All project components: research, requirements, architecture, UX, implementation, verification, documentation |
| Supervisor | Akerke Akanova | Guidance and review of key deliverables and decisions |

## 10.4 Milestones

| Milestone | Date | Content |
|---|---|---|
| Internal 1: diagrams ready | 23 october | System context, use case and component diagrams (draft) |
| Internal 2: UX mockups ready | 23 october | Mockups of key scenarios: procedure selection menu, CPR, blood draw |
| Internal 3: supervisor feedback received | 23-24 october | Review of draft deliverables, list of comments and decisions |
| **Pre-defense 1** | **24 October 2026** | Prototype: a single application with a procedure selection menu and two procedures (CPR and blood draw); proposal, evidence of relevance, literature review, system and technology comparison, requirements, architecture and diagrams, UX mockups, verification plan, project management, supervisor feedback |
| Pre-defense 2 | TBD (to be confirmed by the programme schedule) | User roles, persistent storage of results, instructor view, extended prototype with more procedures |
| Final defense | TBD (to be confirmed by the programme schedule) | Completed platform, verification results, final report |

## 10.5 Risks

**Scales.** Probability: Low < 20%, Medium 20–50%, High > 50%. Impact: Medium = delays a deliverable; High = threatens a milestone or the quality of a key deliverable; Critical = threatens the project aim or the safety/correctness of the training content.

**Owner** of all risks: Anatoliy Tsoy. **Status:** Open unless stated otherwise.

| ID | Risk | Prob. | Impact | Mitigation | Contingency (plan B) | Status |
|---|---|---|---|---|---|---|
| R1 | Medical inaccuracies in training scenarios may teach incorrect procedures | Medium | Critical | Use reliable medical sources and consult medical professionals to validate procedures and instructions | Limit the prototype to procedures with published step-by-step guidelines; mark unvalidated steps as such | Open |
| R2 | VR performance issues may affect the training experience | High | High | Select the target headset early; develop and test a prototype on the actual device | Reduce model detail and effects; fall back to a simplified scene | Open |
| R3 | Lack of medical knowledge may lead to incorrect procedure modeling | High | High | Focus on one specific procedure and use validated step-by-step instructions | Ask the supervisor or a medical contact to review the procedure model before it is finalised | Open |
| R4 | Compatibility problems between the headset, Unity version, and XR framework | Medium | High | Fix the Unity and XR package versions early; test a minimal scene on the target device before building features | Switch to the nearest stable Unity/XR package combination | Open |
| R5 | Difficulty defining objective scoring rules for the procedures | Medium | High | Use clinical guideline values as reference; check scoring against expert assessment on recorded sessions | Use a simple pass/fail checklist per step instead of a detailed score | Open |
| R6 | Development delays due to limited VR experience and excessive scope | High | High | Prioritize a minimum viable product (MVP) with one complete procedure before adding extra features | Cut the second procedure from the pre-defense 1 scope or show it as a demo only | Open |
| R7 | Limited access to VR equipment or insufficient budget | Medium | High | Confirm equipment availability and costs early; avoid features requiring unavailable hardware | Use the Unity XR device simulator for development and demonstration | Open |
| R8 | Privacy or security issues may arise when storing user data and training results | Low | High | Minimize personal data collection and apply appropriate data protection measures | Store results locally or anonymised until a backend is implemented | Open |
| R9 | Single-person team: illness or overload delays the schedule | Medium | High | Keep tasks small and tracked in YouTrack; plan buffer time before each milestone | Reprioritise to MVP scope; agree deadline adjustments with the supervisor | Open |
| R10 | Limited access to medical experts for interviews and validation | Medium | High | Contact experts early and in parallel with the literature review; prepare short, focused questions | Rely on clinical guidelines and supervisor review; clearly mark findings as unverified | Open |

## 10.6 Dependencies

| ID | Task / deliverable | Depends on | Type | YouTrack (task) | YouTrack (depends on) |
|---|---|---|---|---|---|
| D1 | Requirements specification | Evidence of relevance, Literature review, Existing systems comparison | Finish-to-Start | XMT-8 | XMT-3, XMT-5, XMT-6 |
| D2 | Architecture and diagrams | Requirements specification, Technology comparison | Finish-to-Start | XMT-9, XMT-10 | XMT-8, XMT-7 |
| D3 | UX mockups | Requirements specification | Finish-to-Start | XMT-11 | XMT-8 |
| D4 | Verification and evaluation plan | Requirements specification, metrics, reference values from clinical guidelines | Finish-to-Start | XMT-12 | XMT-8 |
| D5 | Prototype (CPR and blood draw) | Technology comparison, Architecture, UX mockups | Finish-to-Start | XMT-17 | XMT-7, XMT-9, XMT-11 |
| D6 | Second procedure | Architecture and procedure module design, Prototype | Finish-to-Start | XMT-18 | XMT-9, XMT-17 |
| D7 | Supervisor feedback | Availability of draft deliverables | Finish-to-Start | XMT-13 | XMT-8, XMT-9, XMT-11, XMT-12 |

**Link between dependencies and risks:** D4 is affected by R5; D5 and D6 by R6; D8 by R1, R3 and R10; D9 by R2, R4 and R7.

The final submission check (XMT-14) depends on all deliverables above.

## 10.7 Next steps

* Select the target headset and build a minimal scene on it (closes R2, R4, R7).
* Complete the architecture and procedure module design, then add further procedures through the procedure module without changes to the core (D2, D6, R6).
* Define scoring rules for the procedures based on clinical guideline values (D4, R5).
* Implement a backend with a database to store trainee results (R8).
* Implement user roles and the instructor view so that instructors can review trainee results.
* Schedule validation of the procedures with a medical expert (D8, R1, R3, R10).
