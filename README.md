# Fencing Lunge Landing Analysis

Applied data analysis and visualization to evaluate **landing mechanics** in the fencing lunge, aiming to distinguish **stable/correct** vs **unstable/incorrect** positions and produce **actionable feedback** for training.

---

## Project Context

This project was originally created in 2022 as a personal side project.  
I have lightly updated the documentation for clarity and reproducibility (no history rewritten).

- **Motivation:** My family and I practice fencing; I wanted a data‑driven way to analyze lunge landing posture.
- **Focus:** **EDA + feature extraction + visualization**, prioritizing interpretability and coaching value over complex modeling.

---

## Overview

- **Goal:** Identify movement/positional patterns associated with correct vs unstable landings in the fencing lunge.
- **Data:** Movement/position data (e.g., joint or segment coordinates, angles, or derived features) collected from lunge attempts.  
  _If you used video → keypoints, briefly note the tool (e.g., MediaPipe/OpenPose). If you used numerical sensor data, describe the source at a high level._
- **Approach:**
  1. Clean and structure data per attempt.
  2. Extract **key features** related to balance and alignment (examples below).
  3. Perform **exploratory data analysis (EDA)** and **visualization** to compare attempts.
  4. Derive **practical criteria** or ranges indicative of “good” landings that athletes/coaches can use.

---

## Example Features (adapt to what the notebook computes)

- Lead knee flexion angle at landing
- Trunk forward‑lean angle near contact
- Rear‑foot vs lead‑foot contact timing
- Stance width / center‑of‑mass projection
- Velocity/acceleration around ground contact
- Consistency/symmetry across repeated attempts

> The exact features depend on the available signals (keypoints vs sensor time series).  
> The notebook (`fencing_launch.ipynb`) demonstrates extracting and visualizing these signals.

---

## Method

- **Preprocessing:** smoothing, normalization (if applied), handling missing points / low keypoint confidence
- **Feature Extraction:** compute angles, distances, temporal events from raw coordinates
- **EDA & Visualization:** distributions, time‑aligned plots across attempts, pairwise plots for separability
- **Interpretation:** define **practical** thresholds or guidance (e.g., suggested angle ranges, stance metrics)

This project is intentionally **model‑light**: the emphasis is on interpretability and technique feedback rather than predictive modeling.

---

## Key Outputs

- Plots comparing **correct vs incorrect** landings (angles over time, joint trajectories, stance measures)
- Summary tables/statistics highlighting stable vs unstable patterns
- Suggested **coaching cues**, e.g., “Maintain knee over toe within X–Y° at contact,” “Reduce trunk lean beyond Z°”

---

## Exit examples
<img width="640" height="480" alt="annotated_image_bad" src="https://github.com/user-attachments/assets/d93bafd1-2c11-4bee-b755-c3c3bacdbf4d" />
<img width="640" height="480" alt="annotated_image_good" src="https://github.com/user-attachments/assets/1a15695c-9969-4a5d-bef2-5a39694f8294" />

