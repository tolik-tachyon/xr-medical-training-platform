# Project Proposal: Development of an AR/VR Application for Professional Training of Medical Specialists

## Project Title

Development of an AR/VR Application for Professional Training of Medical Specialists

## Team

Anatoliy Tsoy

## Supervisor

Akerke Akanova

## Problem Statement

Practical training of medical specialists depends on access to mannequins, simulation centers, instructors, and real clinical cases. These resources are expensive, limited in availability, and hard to scale, so trainees often get few repetitions of critical procedures. Feedback is frequently subjective and delivered late: an instructor can observe only one trainee at a time and cannot objectively measure parameters such as timing, accuracy, or sequence of actions.

AR/VR technologies make it possible to practise procedures repeatedly in a safe, controlled environment and to record objective performance data. However, many existing solutions cover a single procedure, are tied to a specific device or vendor, and are not designed to be extended with new training scenarios. As a result, institutions that need several procedures must adopt several unrelated products. A common, extensible platform with a unified way to define scenarios, evaluate performance, and track progress is therefore needed.

## Target Users

- Trainees: medical students and interns who practise procedures and receive feedback.
- Instructors: teachers and clinical trainers who assign scenarios, review results, and monitor progress.
- Administrators: staff of an educational institution or simulation center who manage users, scenarios, and devices.

Instructor and administrator functions are planned for the next stage of the project.

## Goal

To design and develop a prototype of an extensible AR/VR platform for training medical specialists in clinical procedures, with automated performance assessment, and to evaluate its feasibility using cardiopulmonary resuscitation (CPR) as the first implemented procedure and blood draw as the second.

## Objectives

1. Analyse user needs and the current state of AR/VR training in medical education (literature, existing systems, discussions with user representatives).
2. Specify functional and non-functional requirements with priorities and acceptance criteria.
3. Select key technologies by comparing alternatives against the requirements.
4. Design the platform architecture, including a procedure module that allows new scenarios to be added without changing the core system.
5. Design the user interface and key user scenarios for trainees, with instructor-related scenarios planned for the next stage.
6. Implement a working prototype with two complete procedures (CPR and blood draw), including step guidance, real-time feedback, and a results summary.
7. Implement collection of performance data (e.g. timing, correctness of steps) for assessment; persistent storage and progress tracking are planned for the next stage.
8. Define and carry out a verification and evaluation plan with measurable metrics and a baseline for comparison, including a check that the second procedure was added through the procedure module without changes to the core system.

## Expected Results

- A requirements specification with verifiable acceptance criteria.
- An architecture description with context, use case, and component diagrams.
- UX mockups of the key scenarios.
- A working prototype of the platform with two complete procedures (CPR and blood draw).
- A performance assessment mechanism that records and presents objective results for each session.
- A verification report showing to what extent the requirements and the project aim have been achieved, including evidence that the platform can be extended with a new procedure without changing its core.

## Scope

### In scope

- Core platform: procedure selection, scenario execution, and results review for a session.
- Procedure module with a defined structure for scenarios (steps, conditions, scoring rules).
- Two fully implemented procedures: CPR and blood draw.
- Collection of performance data during a session.
- Verification of the prototype against the defined requirements and metrics.

### Out of scope

Planned for the next stage (pre-defense 2):
- User roles (trainee, instructor, administrator).
- Persistent storage of results and progress tracking.
- Instructor view for reviewing trainee results.

Potential future work:
- Additional procedures (e.g. patient examination, surgical procedures).
- Clinical validation with real patients or certification as a medical training product.
- Support for all AR/VR devices on the market; the prototype targets a limited set of selected devices.
- Integration with external learning management systems.
