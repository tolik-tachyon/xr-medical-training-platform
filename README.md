# AR/VR Application for Professional Training of Medical Specialists

An extensible AR/VR platform for training medical specialists in clinical procedures, with automated performance assessment. The first prototype implements two complete procedure: cardiopulmonary resuscitation (CPR) and taking blood.

> Diploma project, Astana IT University, 2026.

## Problem statement

Practical training of medical specialists depends on mannequins, simulation centers, and instructors. These resources are expensive and limited, so trainees get few repetitions of critical procedures, and feedback is often subjective and delayed. Existing AR/VR solutions usually cover a single procedure and are not designed to be extended with new scenarios. A common, extensible platform with unified scenario definition, performance evaluation, and progress tracking is needed.

## Target users

- **Trainees:** medical students and interns who practise procedures and receive feedback.
- **Instructors:** teachers and clinical trainers who assign scenarios and review results.
- **Administrators:** staff of educational institutions or simulation centers who manage users and scenarios.

## Expected outcomes

- Requirements specification with verifiable acceptance criteria
- Architecture description and diagrams
- UX mockups of key scenarios
- Working prototype with two complete procedure (CPR, Taking Blood)
- Performance assessment mechanism with objective results
- Verification report against defined metrics

## Team and supervision

| Role | Name | Responsibilities |
|---|---|---|
| Student | Anatoliy Tsoy | Development and documenation |
| Supervisor | Akerke Akanova | Project guidance and review of key deliverables |

## Project scope

**In scope**
- Procedure module with a defined scenario structure (steps, conditions, scoring rules)
- Two fully implemented procedure: CPR, Taking blood
- Basic instructor view for reviewing trainee results
- Verification of the prototype against the defined requirements and metrics.

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
| AR/VR engine and XR framework | Unity and XR framework in consideration |
| Target devices | VR helmet |
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
├── docs/        # Documentation and pre-defense materials
├── protoype/
├── .gitignore
└── README.md
```

## Setup, execution, and testing

Will be added as soon as runnable code is available.
