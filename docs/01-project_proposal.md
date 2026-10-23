# 1. Project proposal

## 1.1 Problem statement

Practical training of medical specialists depends on access to mannequins, simulation centers, instructors, and real clinical cases. High-fidelity simulation requires considerable financial investment, dedicated facilities and trained personnel [1]; mannequin-based training needs small groups and more instructors [11], and large cohorts (350–500 students) make small-group follow-up difficult to sustain [10]. As a result, opportunities for repeated practice are often limited [1].

Feedback is frequently subjective and delivered late. Individual assessment with one instructor per student is not realistic in terms of cost and resources [11], and in CPR training human assessment agreed poorly with software-based measurement [6]. In a randomized trial of VR venipuncture training, shorter feedback delay was the mechanism that mediated skill transfer [5].

AR/VR technologies make it possible to practise procedures repeatedly in a safe, controlled environment with immediate feedback [1] and to record objective performance data such as time, attempts and tool pressure [3], [13]. The evidence for learning effectiveness is, however, of low certainty, and VR is regarded as a complement to hands-on training rather than a replacement [1]. The reviewed solutions mostly cover a single procedure on a specific device or setup [5], [11], [12], [13], and none describes a common, documented format for adding new procedures (Section 3.4). This suggests that institutions needing several procedures may have to adopt several unrelated products (an assumption to be confirmed in interviews, Section 2). A common, extensible platform with a unified way to define scenarios, evaluate performance, and track progress is therefore proposed as a design approach, and this project evaluates its feasibility.

## 1.2 Target users

- Trainees: medical students and interns who practise procedures and receive feedback.
- Instructors: teachers and clinical trainers who assign scenarios, review results, and monitor progress.
- Administrators: staff of an educational institution or simulation center who manage users, scenarios, and devices.

Instructor and administrator functions are planned for the next stage of the project.

## 1.3 Aim

To design and develop a prototype of an extensible AR/VR platform for training medical specialists in clinical procedures, with automated performance assessment, and to evaluate its feasibility using cardiopulmonary resuscitation (CPR) as the first implemented procedure and blood draw as the second.

## 1.4 Objectives

1. Analyse user needs and the current state of AR/VR training in medical education (literature, existing systems, discussions with user representatives).
2. Specify functional and non-functional requirements with priorities and acceptance criteria.
3. Select key technologies by comparing alternatives against the requirements.
4. Design the platform architecture, including a procedure module that allows new scenarios to be added without changing the core system.
5. Design the user interface and key user scenarios for trainees, with instructor-related scenarios planned for the next stage.
6. Implement a working prototype with two complete procedures (CPR and blood draw), including step guidance, real-time feedback, and a results summary.
7. Implement collection of performance data (e.g. timing, correctness of steps) for assessment; persistent storage and progress tracking are planned for the next stage.
8. Define and carry out a verification and evaluation plan with measurable metrics and a baseline for comparison (reference values from clinical guidelines and expert assessment of the same sessions), including a check that the second procedure was added through the procedure module without changes to the core system.

## 1.5 Expected outcomes

- A requirements specification with verifiable acceptance criteria.
- An architecture description with context, use case, and component diagrams.
- UX mockups of the key scenarios.
- A working prototype of the platform with two complete procedures (CPR and blood draw).
- A performance assessment mechanism that records and presents objective results for each session.
- A verification report showing to what extent the requirements and the project aim have been achieved, including evidence that the platform can be extended with a new procedure without changing its core.

## 1.6 Project scope

In scope (current stage, prototype):
- Core platform: procedure selection, scenario execution, and results review for a session.
- Procedure module with a defined structure for scenarios (steps, conditions, metrics, scoring rules).
- Two fully implemented procedures: CPR and blood draw.
- Collection of performance data during a session.
- Verification of the prototype against the defined requirements and metrics.

Planned for the next stage (pre-defense 2):
- User roles (trainee, instructor, administrator).
- Persistent storage of results and progress tracking.
- Instructor view for reviewing trainee results.

Out of scope (potential future work):
- Additional procedures beyond CPR and blood draw (e.g. patient examination, surgical procedures).
- Clinical validation with real patients or certification as a medical training product.
- Support for all AR/VR devices on the market; the prototype targets a limited set of selected devices.
- Integration with external learning management systems.
