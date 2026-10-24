# 9. Verification and Evaluation Plan

This section describes how the achievement of the project aim will be demonstrated: that the application supports hands-on training of CPR and blood draw with step checking, immediate feedback and objective scoring, and that new procedures can be added through a common module format. Thresholds in this plan are proposed targets and will be confirmed with the supervisor.

## 9.1 Verification levels

| Level | Question | Methods | Stage |
|-------|----------|---------|-------|
| A. Functional verification | Does each mandatory requirement work as specified? | Acceptance tests with a fixed protocol | Pre-defense 1 (prototype scope), full at pre-defense 2 |
| B. Technical performance | Does the application run smoothly on the target headset? | Unity Profiler, frame time and latency measurement | Pre-defense 1-2 |
| C. Scoring validity | Does automated scoring agree with expert assessment and guideline values? | Comparison against expert checklist and reference values, Cohen's κ | Pre-defense 2 |
| D. Usability and comfort | Is the application usable and tolerable in a 15-minute session? | System Usability Scale (SUS), Simulator Sickness Questionnaire (SSQ) | Pre-defense 2 |
| E. Training effectiveness | Does VR practice improve skill compared with the baseline? | Pilot comparison with a baseline group | Final defense |

## 9.2 Baseline solution

The baseline is conventional training without the VR application: instructional video plus practice on a manikin (CPR) or training arm (blood draw), assessed by an instructor with a checklist. This follows the comparison groups used in the literature: manikin-only simulation in the CPR trial [11], traditional training in the venipuncture trial [5], and video-based modules in the basic care study [9]. The baseline is used in Level E and for reference values in Level C.

## 9.3 Verification of requirements

| Requirement group | Method | Metric | Measurement conditions | Acceptance criterion (proposed) |
|-------------------|--------|--------|------------------------|--------------------------------|
| Procedure execution in VR: CPR and blood draw scenarios run start to finish (FR-1, FR-7) | Scripted acceptance test, each procedure run end to end | Scenario completed without crash or blocking error | Target headset, release build, 10 runs per procedure | 10/10 runs complete |
| Step guidance and step checking (FR-2, FR-3) | Test cases with correct and deliberately wrong actions for each step | Share of steps where the system classifies the action correctly | Fixed test script, same tester, guideline step list as reference | 100% of defined steps handled; every wrong action detected in the script |
| Immediate feedback (FR-4) | Timed test from action to feedback | Feedback delay in seconds | Target headset, 20 actions per procedure | Median delay at most 1 s (the venipuncture system in [5] reported 9 s) |
| CPR measurement: rate, count, depth (FR-5, FR-6) | Compare system values with reference values from guidelines [35] and with an independent reference measurement or manual count | Rate (compressions/min), count, depth estimate error | Same input device, 5 sessions, fixed duration | Rate and count error at most 5%; depth error limits to be set after checking input-device accuracy [1][6] |
| Automated scoring and step data (FR-8, FR-9) | Compare automated score with expert checklist score on the same sessions | Cohen's κ (agreement), score difference | At least 10 recorded sessions, scored independently by one expert | κ at least 0.61 (commonly interpreted as substantial agreement); for reference, κ = 0.81 in [5] |
| End-of-session review (FR-10) | Acceptance test | Review screen shows per-step result, time and errors | Run after each scenario | Present and correct for all recorded sessions |
| Extensible procedure module (FR-11, NFR-8) | Add a new test procedure through the module definition without changing core code | Number of core files changed; time to add | One developer, one dummy procedure | 0 core files changed |
| Repeatable practice (FR-12) | Acceptance test | Session can be restarted and repeated | 5 repeats in a row | No state carried over incorrectly |
| Performance (NFR-1) | Unity Profiler and on-device frame measurement | Frame rate, frame time, latency | Target headset, release build, full scenario | Stable at the headset's target refresh rate (72 FPS or higher), no sustained drops; confirm on real device when available |
| Standalone headset (NFR-2) | Build and run on target device | Runs without PC connection | Meta Quest 3 / 2 | Installs and runs standalone |
| Comfort and session length (NFR-4, NFR-9) | SSQ before and after, session timer | SSQ total score change, symptoms reported, session length | 15-minute scenario | Session at most 15 minutes; no participant withdraws because of symptoms |
| Guideline traceability (NFR-5, R1) | Review of step list against guideline text by an expert | Each step linked to a guideline reference; expert sign-off | Once per procedure | 100% of steps referenced; expert comments resolved |
| Usability | SUS questionnaire | SUS score (0-100) | After the pilot session, each participant | Mean at least 68 (a commonly used benchmark for average usability) |

## 9.4 Evaluation of training effectiveness (Level E)

Goal: show whether VR practice can improve CPR and blood draw skill compared with the baseline, within the limits of a small pilot.

Design:
- Two groups: baseline only versus baseline plus VR practice. The VR group receives the application as an addition to hands-on practice, as in [11], because the literature treats VR as a complement, not a replacement [1][7][10].
- Participants: medical or nursing students on a voluntary basis, with informed consent. Planned sample: as many as can be recruited; the result is a pilot and will not be presented as proof of superiority.
- Procedure: pre-test, training (baseline or baseline plus VR), post-test; optional retention test after 1-2 weeks, because retention is the weakest area of evidence in [1].

Outcome measures:
- Instructor checklist score per step (primary).
- CPR rate and depth versus guideline values, and time to complete the procedure, plus error count.
- Self-reported confidence (short questionnaire).
- SUS and SSQ for the VR group.

Analysis:
- Descriptive statistics and effect sizes; non-parametric tests (for example Mann-Whitney U) because of small samples.
- Limitations are reported openly: small sample, short follow-up, single institution, possible novelty effect on usability ratings (as noted in [11]).

## 9.5 Test tooling

- Unity Test Framework (EditMode and PlayMode tests) for step logic, scoring rules and the procedure module loader.
- Unity Profiler and on-device measurement for performance.
- A written manual test protocol (test case ID, linked requirement, steps, expected result, result, date) stored in the Git repository, so that every result is traceable to a requirement and a build version.
- Recorded session data (per-step results, timestamps) exported for the scoring comparison.

## 9.6 Schedule

| Stage | Verification activities |
|-------|------------------------|
| Pre-defense 1 | Level A and B for the implemented prototype scope; this plan |
| Pre-defense 2 | Level A complete, Level B on real headset if available, Levels C and D; backend and instructor view tests if implemented |
| Final defense | Level E pilot and analysis, final acceptance report |

## 9.7 Limitations and risks

- No physical headset is currently available, so on-device performance and comfort measurements (NFR-1, NFR-4) depend on getting access to one. Until then, tests run in the XR Device Simulator and results are marked as simulator-only.
- Depth measurement for CPR depends on the input method; headset and controllers can limit accuracy [1][6]. The accuracy limit will be measured before the depth criterion is fixed.
- Recruiting enough participants for Level E may not be possible; in that case the results are reported as a feasibility study.
- Expert availability for checklist scoring and guideline sign-off is a dependency (R1, R5).
