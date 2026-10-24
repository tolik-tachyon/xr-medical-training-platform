# 2. Evidence of Relevance

## 2.1 Method

- Format: structured written interviews through an online form, 19 open questions in four blocks (background, current training practice, difficulties and barriers, expectations of a VR platform). The full question list is in Appendix A.
- Period: 23-24 October 2026.
- Respondents: 3 user representatives (Table 2.1). All three gave explicit consent to use their answers; answers are anonymised.
- Purpose: to check whether the problem in the project proposal exists in practice, to collect user requirements, and to separate verified findings from assumptions.

Table 2.1. Respondents

| ID | Role | Specialty / year | Experience with VR, AR or computer simulators |
|----|------|------------------|----------------------------------------------|
| R1 | Medical instructor | Neurology | None |
| R2 | Medical student | 5th year | None |
| R3 | Medical student | Surgery, 4th year | None |

## 2.2 Findings

Table 2.2. Summary of answers

| Topic | R1 (instructor) | R2 (student, 5th year) | R3 (student, 4th year) |
|-------|-----------------|------------------------|------------------------|
| CPR training tools | Face-to-face training, AED, manikin | Simulator | CPR manikin |
| Blood collection / IV training | Trainer to trainee | Demonstration on a patient | Theory, simulation and manikin practice |
| Repetitions per procedure | 2-3 | 3 | "Hundreds of times" (cumulative, as stated) |
| Assessment | Success rate | Theory and practical exams | Timed practical check-offs; zero-tolerance checklist for safety and critical errors; live-patient evaluation |
| Feedback timing | Immediately | After the examination | Immediately in the lab; within minutes in clinical rotations |
| Hardest part | Short training time | Intense training | Performance anxiety and the tactile "feel" of a vein |
| Typical mistakes | Chest compression, uncertain actions | Tactical mistakes | Mechanical errors caused by nervousness or procedural shortcuts |
| Barriers to more practice | Fear of failing | Time limitation | Institutional cost, safety regulations, shortage of clinical placements |
| Useful platform features | Simulation for repeated training | Training at own pace | No answer ("I don't know") |
| Performance data wanted | Analysis of mistakes and speed | Mistakes and how to improve them | No answer |
| Barriers to using a platform | Bugs, inconvenience of wearing a headset | Availability | None stated |
| Motion sickness with VR | No | No | No answer |

## 2.3 What the evidence supports

Table 2.3. Findings and their effect on requirements

| # | Finding | Evidence | Effect on requirements |
|---|---------|----------|------------------------|
| E1 | Current CPR and blood draw training is done with manikins, simulators and trainer demonstration | R1, R2, R3 | Confirms the baseline for evaluation (Section 9): manikin training with instructor assessment |
| E2 | Practice time is limited, and students want to repeat procedures | R1 (2-3 repetitions, short training time, wants repeated simulation), R2 (3 repetitions, time limitation, wants own pace), R3 (cost, safety rules and placement shortage limit practice) | Supports repeatable practice at the learner's own pace (FR-12) |
| E3 | Assessment is checklist and time based, with critical-error rules | R1 (success rate), R3 (timed check-offs, zero-tolerance checklist) | Supports step-level scoring and time measurement (FR-8, FR-9) |
| E4 | Feedback timing varies; one student receives it only after the examination | R2; R1 and R3 report immediate feedback in the lab | Supports immediate feedback after each step (FR-4) |
| E5 | Typical mistakes are chest compression errors, uncertain actions, tactical mistakes and nervous mechanical errors | R1, R2, R3 | Supports step order and condition checking (FR-3) and CPR compression measurement (FR-5, FR-6) |
| E6 | Fear of failing and performance anxiety slow learning | R1, R3 | Supports safe repeated practice in a virtual environment (FR-12) |
| E7 | Users want to see mistakes, speed and how to improve | R1, R2 | Supports the results summary with errors, time and score (FR-9, FR-10) |
| E8 | Concerns: bugs, discomfort of wearing a headset, availability | R1, R2 | Supports stable operation (NFR-7), comfort and session length (NFR-4, NFR-9) and a standalone headset that does not need a PC (NFR-2) |
| E9 | The instructor wants performance data (mistakes and speed) | R1 | Partial support for the planned instructor view (FR-14, FR-15, P2); not confirmed by other respondents |

## 2.4 Verified findings and assumptions

Table 2.4. Evidence level

| Statement | Level | Basis |
|-----------|-------|-------|
| Manikin-based training is the current practice | Verified (3 of 3) | E1 |
| Practice time is limited and repeated practice is wanted | Verified (3 of 3) | E2 |
| Feedback should be immediate and show mistakes | Verified in part (2 of 3 ask for mistake analysis; one student receives feedback late) | E4, E7 |
| Chest compression is a common source of mistakes | Reported by 1 respondent (R1) | E5; also supported by literature [6] |
| An instructor view is needed | Reported by 1 respondent (R1) | E9; remains a planned feature (P2) |
| Users will accept VR | Assumption | No respondent has used VR; no one reported motion sickness (R1, R2), but without VR experience this is not evidence |
| Headset comfort and cybersickness are acceptable in a 15-minute session | Assumption | Literature reports dizziness and headaches [11]; to be measured in Section 9 |
| Compression depth can be estimated reliably with the chosen input device | Assumption | Not covered by the interviews; depends on the device [1][6] |

## 2.5 Limitations

- Small sample (3 respondents), convenience sampling, no information on institution or region beyond role and year.
- Written form, not live discussions: answers are short and cannot be clarified. R3 did not answer the questions about platform features and data, and some answers are general descriptions of training rather than personal experience.
- Only one instructor; students are from different specialties.
- No respondent has used VR or AR, so findings describe the problem and expectations, not the acceptance of the solution.
- Self-reported data.

## 2.6 Next steps

- Follow up with live discussions (short calls) with the instructor and at least one student after the prototype demo, to test the prototype scenarios (Section 8).
- Add 1-2 respondents, preferably an instructor of emergency medicine or nursing, to confirm findings E5 and E9.
- Record each new discussion in Table 2.2 and update the evidence level in Table 2.4.

## Appendix A. Interview questions

- Background: current role; specialty, year of study or professional experience.
- Current training: how CPR is taught and with which tools; how blood collection and intravenous procedures are taught; number of repetitions and whether it is enough; how performance is assessed; how soon and in what way feedback is given.
- Difficulties: the hardest part; the most frequent mistakes; what prevents more practice; an example of a failed training session.
- Technology: experience with VR, AR or computer simulators and impressions; motion sickness or discomfort in VR.
- Expectations: useful features; missing features and concerns; performance data that matters; what could prevent use; anything not asked.
