# 8. UX / Prototype

Project: Development of an AR/VR Application for Professional Training of Medical Specialists

This section shows how users interact with the application in the key scenarios of the prototype (P1). The scenarios follow the use cases of Section 7 (UC-1 to UC-5). Each screen is marked as implemented in the Unity prototype or as a mockup. All screens below are mockups; numbers on them (time, score, rate, count) are illustrative.

## 8.1 Interaction model

- Device: standalone XR headset (Meta Quest), two controllers (Section 5).
- Menus and panels: world-space UI operated with a controller ray and the trigger button.
- Procedure actions: performed in the virtual scene with the controllers (grab tools, press on the manikin chest, and so on); the Input Adapter converts them into device-independent action events (Section 7).
- Session length: up to 15 minutes (NFR-9).
- Design principles, taken from the interviews (Section 2) and the literature (Section 3):
  - guidance for the current step is always visible (FR-2);
  - feedback appears immediately after an action (FR-4, E4);
  - the trainee can repeat a procedure without restarting the application (FR-12, E2);
  - the summary shows mistakes, time and score (FR-10, E7).

## 8.2 Key user scenarios

### Scenario 1: Select a procedure (UC-1)

1. The trainee puts on the headset and sees the main menu with the list of procedures (CPR, blood draw).
2. The trainee points the controller ray at a procedure and presses the trigger.
3. The training scene for the selected procedure loads.

![S1 Main menu](img/S1_main_menu.png)

*Fig. 8.1. S1: main menu (mockup).*

### Scenario 2: Perform a procedure with step guidance (UC-2, UC-3)

1. The instruction panel shows the current step (for example "Check responsiveness") and the step number.
2. The trainee performs the action in the scene.
3. The system checks the action against the step condition.
4. If the action is correct, the feedback panel shows a confirmation and the next step becomes active.
5. If the action is wrong or out of order, the feedback panel shows the error, and the step stays active until the trainee corrects it.
6. In the CPR procedure, the current compression rate and count are shown during the compression step.

![S2 Training scene with instruction panel](img/S2_training_scene.png)

*Fig. 8.2. S2: training scene with the instruction panel and CPR metrics (mockup).*

![S3 Correct and incorrect feedback](img/S3_feedback.png)

*Fig. 8.3. S3: correct and incorrect feedback (mockup).*

### Scenario 3: View the results summary (UC-4)

After the last step the summary screen shows: total time, number of completed, missed and incorrect steps, score, and for CPR the compression rate and count (FR-10).

![S4 Results summary](img/S4_results_summary.png)

*Fig. 8.4. S4: results summary (mockup, illustrative data).*

### Scenario 4: Repeat or return to the menu (UC-5)

From the summary screen the trainee chooses "Repeat" to restart the same procedure or "Menu" to return to the procedure list (FR-12).

![S5 Repeat / menu buttons](img/S5_repeat_menu.png)

*Fig. 8.5. S5: repeat / menu buttons at the end of a session (mockup).*

### Planned (P2): Instructor view (UC-7)

A mockup of the instructor screen listing trainee sessions with score, time and errors per step. This screen is a mockup only and is not implemented in P1.

![S6 Instructor view (P2)](img/S6_instructor_view_P2.png)

*Fig. 8.6. S6: instructor view (mockup, planned for P2, illustrative data).*

## 8.3 CPR procedure flow (activity diagram)

The diagram shows the flow of the CPR procedure from the trainee's point of view, including the error case: a wrong or out-of-order action is rejected, feedback is shown, and the same step stays active until the trainee corrects it (FR-3, FR-4). The step list follows the CPR procedure definition (Section 7.5) and the guideline reference [35]. The sequence of component calls is shown in Section 7.6.

```mermaid
flowchart TD
  Start([Start: trainee selects CPR]) --> Load[System loads CPR definition and scene]
  Load --> Step[Show instruction for current step]
  Step --> Act[Trainee performs action]
  Act --> Check{Action correct<br/>and in order?}
  Check -- No --> Err[Show error feedback<br/>record step as incorrect]
  Err --> Step
  Check -- Yes --> Ok[Show confirmation feedback<br/>record time and result]
  Ok --> Comp{Compression step?}
  Comp -- Yes --> Metrics[Measure compression rate and count<br/>show current values]
  Metrics --> More
  Comp -- No --> More{More steps?}
  More -- Yes --> Next[Activate next step]
  Next --> Step
  More -- No --> Score[Apply scoring rules]
  Score --> Summary[Show results summary:<br/>time, steps, score, rate, count]
  Summary --> Choice{Trainee choice}
  Choice -- Repeat --> Load
  Choice -- Menu --> End([Return to main menu])
```

Steps of the CPR procedure (example wording used in the mockups; to be aligned with the definition file):

| Step | Instruction | Condition |
|------|-------------|-----------|
| S1 | Check responsiveness | Action: check_response |
| S2 | Call for help | Action: call_help |
| S3 | Check breathing | Action: check_breathing |
| S4 | Perform chest compressions | Metric: rate and count within reference range |
| S5 | Use the AED (optional, if included in the prototype) | Action: use_aed |

## 8.4 Screen inventory

| Screen | Use case | Requirements | Status |
|--------|----------|--------------|--------|
| S1 Main menu | UC-1 | FR-1 | Mockup |
| S2 Training scene with instruction panel | UC-2 | FR-2, FR-3 | Mockup |
| S3 Feedback panel | UC-3 | FR-4 | Mockup |
| S4 Results summary | UC-4 | FR-9, FR-10 | Mockup |
| S5 Repeat / menu | UC-5 | FR-12 | Mockup |
| S6 Instructor view | UC-7 | FR-14, FR-15 | Mockup, P2 |

## 8.5 Interaction table

| User action | Input | System response | Requirement |
|-------------|-------|-----------------|-------------|
| Select a procedure | Controller ray and trigger | Loads the procedure definition and scene | FR-1 |
| Perform a procedure step | Controller action in the scene (grab, press, move) | Checks the condition, shows feedback, activates the next step | FR-2, FR-3, FR-4 |
| Perform chest compressions (CPR) | Controller movement over the manikin chest | Counts compressions and shows the rate; depth is estimated if the input device allows it | FR-5, FR-6 |
| Finish the procedure | Last step completed | Shows the results summary | FR-10 |
| Repeat or return | Controller ray and trigger | Restarts the procedure or opens the menu | FR-12 |

## 8.6 Limitations of the prototype

- Screens marked as mockup are not yet implemented in Unity.
- Interaction was tested in the XR Device Simulator; testing on a physical headset depends on getting access to one (Section 9).
- Compression depth depends on the input device and is not yet verified.
- Hand tracking is not used in P1; interaction is controller-based.
