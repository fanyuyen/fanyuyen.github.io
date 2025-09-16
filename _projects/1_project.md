---
layout: page
title: NNAR
description: A augmented reality yool for real-time optode/electrode placement
img: assets/img/12.jpg
importance: 1
category: work
---

**TL;DR**  
NeuroNavigatAR (NNAR) is an open-source augmented reality tool that uses fast facial-landmark tracking and atlas registration to *predict and overlay* 10–20/10–10/10–5 head landmarks in real time. It improves consistency and speeds up fNIRS/EEG cap placement without needing digitizers or MRI.

---

## Why it matters
- **Problem:** Longitudinal and group EEG/fNIRS studies suffer when caps aren’t placed consistently. Tape-measure workflows are slow and operator-dependent; prefab caps can shift; post-hoc digitizing doesn’t help *during* setup.  
- **Goal:** Provide *real-time* visual guidance for placing probes/caps accurately and repeatably across sessions and subjects.

---

## What NNAR does
- Tracks **468 facial landmarks** per frame (MediaPipe) and estimates key cranial points (Nz, LPA, RPA, Iz, Cz) via a **pre-computed face→head mapping** learned from a **1,000+ subject** 3-D head library (LYHM).
- Registers **atlas-derived 10–20/10–10/10–5** positions to the individual’s head in the camera stream and overlays them **live** (~15 FPS on a laptop).
- Simple GUI to pick atlas (adult or age-matched), system density, and apply small manual offsets if needed.

---

## How it works (short version)
   Detect facial landmarks → predict cranial landmarks → register atlas → render 10–20 overlays on the video feed.

---

## Key results
- **Speed:** ~15 FPS on a MacBook Air (M1).
- **Accuracy (10–5 landmarks):**  
  - Adult atlas (Colin27): **1.52 cm** median error  
  - **Age-matched** atlases: **1.33 cm**  
  - **Subject-specific head surface:** **0.75 cm** (lower bound)
- **Cranial landmark prediction (linear model):** median errors ≈ **0.87–1.75 cm** (LPA, RPA best; Iz higher).  
- **Consistency:** Stable across repeated sessions (no significant accuracy difference across adult age groups); repeatability demo on a human subject showed small tracking errors (e.g., FpZ ≈ **0.11–0.13 cm** vs. fiducials in two sessions).  
- **Spatial pattern:** Forehead/anterior landmarks are most accurate; errors increase toward the posterior (limited camera view & hair occlusion).

---

## Open source

- **Code:** <https://github.com/COTILab/NeuroNavigatAR>  

---

## Citation
Yen, F.-Y., Lin, Y.-A., & Fang, Q. *Improving neuroimaging headgear placement robustness using facial-landmark guided augmented reality.  
**Keywords:** fNIRS, EEG, 10–20 system, augmented reality, computer vision, neuroimaging

