# 5. Technology Comparison

This section compares alternatives for four key technical decisions. Each decision is evaluated against criteria derived from the requirements specification (Section 6). Decisions 1-3 are applied in the pre-defense 1 prototype. Decision 4 is a preliminary choice, planned for pre-defense 2.

## 5.1 Summary of decisions

| # | Decision | Alternatives considered | Selected | Status |
|---|----------|-------------------------|----------|--------|
| 1 | Application engine | Unity [14]; Unreal Engine [17]; WebXR [18] | Unity | Applied in prototype |
| 2 | XR interaction layer | XR Interaction Toolkit + OpenXR [14][15]; Meta XR SDK [16]; SteamVR (OpenVR) [19] | XR Interaction Toolkit + OpenXR | Applied in prototype |
| 3 | Target device | Meta Quest 2/3 [16]; PCVR (SteamVR headsets) [19]; Pico 4 [20] | Meta Quest 3 (Quest 2 as compatible fallback) | Selected, hardware not yet available |
| 4 | Backend and result storage | Local storage (JSON/SQLite); Spring Boot + PostgreSQL [21][22]; Firebase [23] | Spring Boot + PostgreSQL (REST) | Preliminary, pre-defense 2 |

## 5.2 Decision 1: Application engine

Requirement drivers: multi-procedure extensibility, 3D interaction and physics, development time, team experience, performance on standalone headsets.

| Criterion | Unity [14] | Unreal Engine [17] | WebXR (three.js / A-Frame) [18] |
|-----------|-----------|--------------------|---------------------------------|
| Standalone headset support | Supported for Quest via OpenXR [14][16] | Supported for XR devices [17] | Via browser, performance depends on the browser and device [18] |
| Extensibility (new procedures as scenes/modules) | High (scenes, prefabs, ScriptableObjects) [14] | High (levels, Blueprints) [17] | Medium (manual structure) |
| Learning curve and team experience | Low: C#, existing team experience | High: C++/Blueprints, no team experience | Medium: JavaScript, no built-in physics engine |
| Physics and interaction tooling | Built in, plus XR Interaction Toolkit [14] | Built in [17] | Requires third-party libraries [18] |
| Build size and hardware requirements | Moderate | Higher | Lowest, but browser-dependent |
| Asset ecosystem for 3D content | Large (Asset Store) [14] | Large (Fab marketplace) [17] | Small |

Decision: **Unity**. It fits the extensibility requirement (each procedure is an independent scene/module), matches existing team experience, and the prototype is already built on it. Unreal offers higher visual fidelity but adds learning cost and heavier builds without a corresponding requirement. WebXR is easy to distribute but has limited performance and tooling for complex interactions [18].

## 5.3 Decision 2: XR interaction layer

Requirement drivers: hand/controller interaction, hardware independence, ability to develop without a headset.

| Criterion | XR Interaction Toolkit + OpenXR [14][15] | Meta XR SDK [16] | SteamVR (OpenVR) [19] |
|-----------|------------------------------------------|------------------|-----------------------|
| Vendor independence | High (OpenXR is an open standard) [15] | Low (Meta devices) [16] | Medium (PC headsets) [19] |
| Standalone Quest support | Yes, via OpenXR plugin [14][16] | Yes, native [16] | No (PC only) [19] |
| Development without headset | Yes (XR Device Simulator) [14] | Limited | Limited |
| Ready-made interactions (grab, poke, UI) | Yes, built in [14] | Yes [16] | Yes [19] |
| Future portability to other headsets | High [15] | Low [16] | Medium [19] |

Decision: **XR Interaction Toolkit + OpenXR**. Hardware independence supports the platform's long-term extensibility [15], and the XR Device Simulator allows development and testing without access to a physical headset [14], which is a current project constraint.

## 5.4 Decision 3: Target device

Requirement drivers: no dependency on a powerful PC, accessibility for a university, OpenXR support, cost.

| Criterion | Meta Quest 2/3 [16] | PCVR (SteamVR headsets) [19] | Pico 4 [20] |
|-----------|---------------------|------------------------------|-------------|
| Standalone operation | Yes [16] | No, requires a capable PC [19] | Yes [20] |
| Hardware cost | Moderate | High (headset plus PC) | Moderate |
| OpenXR support | Yes [16] | Yes [15][19] | Yes [20] |
| Developer ecosystem and documentation | Large [16] | Large [19] | Smaller [20] |
| Suitability for classroom deployment | High (no PC per station) | Low (PC per station) | Medium |

Decision: **Meta Quest 3** (Quest 2 compatible). Standalone operation removes the need for a PC per training station [16], and the developer documentation covers Unity and OpenXR workflows [16]. Because the choice goes through OpenXR [15], the application is not locked to a single device. Limitation: performance measurements on the real device are deferred until hardware access is available.

## 5.5 Decision 4: Backend and result storage (preliminary)

Planned for pre-defense 2. Required once roles, persistent result storage and the instructor view are introduced.

Requirement drivers: instructors view results of multiple trainees, role-based access, structured result data, team experience.

| Criterion | Local storage (JSON/SQLite) | Spring Boot + PostgreSQL [21][22] | Firebase [23] |
|-----------|-----------------------------|-----------------------------------|---------------|
| Shared results across devices (instructor view) | No | Yes [21][22] | Yes [23] |
| Role-based access control | Not supported | Spring Security [21] | Firebase Authentication and security rules [23] |
| Structured/relational result queries | Limited | Strong (SQL) [22] | Document-based (NoSQL) data model [23] |
| Team experience | High | High (Java Spring Boot) | Low |
| Control over data and hosting | Full, but local only | Full | Vendor-hosted, vendor lock-in [23] |
| Implementation effort | Lowest | Moderate | Low to moderate |

Decision: **Spring Boot + PostgreSQL (REST API)**. It supports the instructor view and roles [21], fits relational data (users, procedures, sessions, step-level results) [22], and matches existing team experience. Local storage is retained as a prototype-stage fallback until the backend is introduced.

## 5.6 Conclusion

The selected stack (Unity, XR Interaction Toolkit with OpenXR, Meta Quest as the target device, and a planned Spring Boot + PostgreSQL backend) is justified by the extensibility, hardware-independence and team-experience requirements. Choices for the engine, interaction layer and device are already reflected in the prototype. The backend choice is preliminary and will be confirmed at pre-defense 2.
