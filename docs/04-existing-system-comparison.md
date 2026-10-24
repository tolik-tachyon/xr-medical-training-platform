# 4. Existing System Comparison

This section compares four existing commercial VR training systems against eight criteria. Selection rationale: the systems are used in medical education, run on VR headsets, and cover different training domains (surgery, clinical scenarios, resuscitation), so together they show what the market offers. Information is taken from vendor materials and independent reviews listed in References; where a source does not state a capability, the cell says "not stated" instead of assuming.

## 4.1 Systems reviewed

- Osso VR: VR surgical and procedural training platform with integrated analytics [24][26].
- Oxford Medical Simulation (OMS): VR clinical scenario simulation for nursing and medical education [28][29].
- Health Scholars: voice-driven VR training for Advanced Cardiac Life Support (ACLS) [30][31].
- Fundamental Surgery (FundamentalVR): VR surgical simulation platform with haptic feedback [32][33].

## 4.2 Comparison

| Criterion | Osso VR | Oxford Medical Simulation | Health Scholars (ACLS) | Fundamental Surgery | Proposed project |
|-----------|---------|---------------------------|------------------------|---------------------|------------------|
| 1. Technology | VR headset [26] | Screen-based or VR headset [28] | VR headset [30] | VR, with haptic devices in the HapticVR mode [32][33] | VR (Unity, OpenXR) |
| 2. Target hardware | Standalone headsets such as Meta Quest [24]; dedicated headsets and physical space required [27] | Headset-based; Quest 2 used in an NHS pilot [29] | Meta Quest 2 [30] | Standalone headsets (Quest, Vive Focus Plus) or PC with headset and haptic arms [32] | Meta Quest 3 (Quest 2 compatible) |
| 3. Procedures covered | Surgical and medical procedures, orthopedics library [26] | 200+ clinical scenarios, including paediatrics, emergencies and bedside procedures [29] | ACLS scenarios; learner directs a virtual team to shock, give medication or perform CPR [30] | Orthopedic surgical procedures [34] | CPR and blood draw (prototype); more procedures planned |
| 4. Hands-on basic skills (CPR compressions, blood draw) | Not stated | Not stated | Not stated; CPR is directed by voice, not performed by the learner [30] | Not stated | Yes, both are implemented in the prototype |
| 5. Customization and extensibility | Custom modules developed by the vendor [25]; a reviewer notes limited customization for institution-specific protocols [27] | Authoring platform (OMS Create) for modifying or building scenarios [28] | Not stated | Not stated | Procedures added as independent modules by the institution |
| 6. Automated assessment and feedback | Integrated assessment and analytics [26] | Personal feedback, guided reflection and scores [28] | Validates competencies via the simulation [30] | Learner progress monitored at each surgical step [33] | Basic feedback in the prototype (to be aligned with Section 6) |
| 7. Instructor view and analytics | Analytics and reports at individual and organizational level [26] | Analytics for administrators, faculty and learners [28] | Not stated | Remote instructor dashboard [33] | Deferred to pre-defense 2 |
| 8. Licensing model | Commercial, enterprise platform [24] | Commercial: pay per use, library or tiered pricing, contact vendor [28] | Commercial, pricing not stated | Commercial SaaS [34] | Developed in-house, institution-owned |

## 4.3 Analysis

- All four reviewed systems are proprietary commercial products. Each source describes either vendor-built content [25], a vendor authoring tool [28], or does not mention customization.
- Coverage is concentrated in surgery [26][34], clinical decision-making scenarios [28] and ACLS team leadership [30]. The reviewed sources do not state support for hands-on basic skills such as CPR compressions or blood draw.
- Academic prototypes in the literature review address individual procedures: CPR training with immersive VR [11], blood collection [12] and airway management [13]. They do not offer a multi-procedure platform.
- Analytics and instructor views are common among commercial systems [26][28][33]. In the proposed project this capability is planned for pre-defense 2, so it is currently a gap relative to the competitors.

## 4.4 Conclusion

Within the reviewed sources, no system combines (a) hands-on basic procedures (CPR, blood draw), (b) institution-controlled extensibility and (c) a low-cost standalone headset target. This is the niche for the proposed platform. Limitations of this comparison: only four systems were reviewed, much of the evidence comes from vendor materials, and "not stated" means the capability was not found in the sources, not that it is absent.
