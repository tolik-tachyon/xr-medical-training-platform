# AR/VR Application for Professional Training of Medical Specialists

An extensible AR/VR platform for training medical specialists in clinical procedures, with automated performance assessment. The first prototype implements two complete procedures: cardiopulmonary resuscitation (CPR) and blood draw.

> Diploma project, Astana IT University, 2026.

## Problem statement

Practical training of medical specialists depends on mannequins, simulation centers, and instructors. These resources are expensive and limited, so trainees get few repetitions of critical procedures, and feedback is often subjective and delayed. Existing AR/VR solutions usually cover a single procedure and are not designed to be extended with new scenarios. A common, extensible platform with unified scenario definition, performance evaluation, and progress tracking is needed.

## Target users

- **Trainees:** medical students and interns who practise procedures and receive feedback.
- **Instructors:** teachers and clinical trainers who assign scenarios and review results.
- **Administrators:** staff of educational institutions or simulation centers who manage users and scenarios.

Instructor and administrator functions are planned for the next stage of the project.

## Expected outcomes

- Requirements specification with verifiable acceptance criteria
- Architecture description and diagrams
- UX mockups of key scenarios
- Working prototype with two complete procedures (CPR and blood draw)
- Performance assessment mechanism with objective results for each session
- Verification report against defined metrics, including evidence that the platform can be extended with a new procedure without changing its core

## Team and supervision

| Role | Name | Responsibilities |
|---|---|---|
| Student | Anatoliy Tsoy | Development and documentation |
| Supervisor | Akerke Akanova | Project guidance and review of key deliverables |

## Project scope

**In scope (current stage, prototype)**
- Core platform: procedure selection, scenario execution, and results review for a session
- Procedure module with a defined scenario structure (steps, conditions, scoring rules)
- Two fully implemented procedures: CPR and blood draw
- Collection of performance data during a session
- Verification of the prototype against the defined requirements and metrics

**Planned for the next stage (pre-defense 2)**
- User roles (trainee, instructor, administrator)
- Persistent storage of results and progress tracking
- Instructor view for reviewing trainee results

**Out of scope (future work)**
- Additional procedures (e.g. patient examination, surgical procedures)
- Clinical validation or certification as a medical training product
- Support for all AR/VR devices on the market
- Integration with external learning management systems

## Current status

**Stage:** Pre-defense 1 (planning and design)

- [x] Project proposal
- [ ] Evidence of relevance
- [ ] Literature review
- [ ] Existing system and technology comparison
- [ ] Requirements specification
- [ ] Architecture and diagrams
- [ ] UX mockups
- [ ] Verification and evaluation plan
- [ ] Prototype implementation

## Selected technologies

| Area | Choice |
|---|---|
| AR/VR engine and XR framework | Unity; XR framework in consideration |
| Target devices | VR headset (model in consideration) |
| Server platform | In consideration |
| Data storage | In consideration |
| Component interaction | In consideration |

## Links

- YouTrack Agile Board: https://xr-medical-training-platform.youtrack.cloud/agiles/204-1/current
- Documentation: In progress
- UX mockups: In consideration

## Repository structure

```
.
├── docs/         # Documentation and pre-defense materials
├── prototype/    # Unity project
├── .gitignore
└── README.md
```

## Setup, execution, and testing

Will be added as soon as runnable code is available.
