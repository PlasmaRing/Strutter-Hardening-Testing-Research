# Effectiveness of Anti-Hook, Root Detection, and Integrity Check for Flutter-Based Android Applications

This repository contains the research artifacts, testing applications, and participant evaluation data used in the study titled **"Effectiveness of Anti-Hook, Root Detection, and Integrity Check for Flutter-Based Android Applications"**.

## Repository Structure

- **apps/**  
  Contains the Android application packages (APKs) used in this research:
  - `hardened/` — Version with **SSL Pinning**, plus additional runtime protections such as **Integrity Verification**, **Anti-Hooking Detection**, and **Root Detection**.  
  - `not_hardened/` — Baseline version that implements **SSL Pinning only**, without additional runtime protection mechanisms.

- **data/**  
  Contains participant evaluation results (`P1–P5`), each represented as an Excel file (`.xlsx`) with multiple sheets:  
  **Result**, **Bio Data**, **Post Test Questionnaire**, and **Documentation**.

- **DETECTION_MECHANISM.md**  
  Describes the detection and testing methodology used to evaluate the implementation of **Integrity Verification**, **Anti-Hooking Detection**, and **Root Detection** within the hardened application.

## File Naming Convention

### Participant Data

| File Name | Description |
|------------|--------------|
| `P1.xlsx` | Participant 1 evaluation data |
| `P2.xlsx` | Participant 2 evaluation data |
| `P3.xlsx` | Participant 3 evaluation data |
| `P4.xlsx` | Participant 4 evaluation data |
| `P5.xlsx` | Participant 5 evaluation data |

Each `.xlsx` file represents the testing output submitted by individual evaluators (P1–P5).  
Please note that responses may vary, as each evaluator conducted independent testing and filled in their data individually.

Each file includes four main sheets:
1. **Result** — Contains testing details such as the date and duration of each interception attempt, the bypass approach used, and the number of detections triggered during hardened app testing.  
2. **Bio Data** — Provides evaluator information, including professional background, device type, and hardware specifications.  
3. **Post Test Questionnaire** — Summarizes tools and methods used, difficulty ratings of the protection mechanisms, overall assessment, and feedback or recommendations.  
4. **Documentation** — Contains screenshots and supporting materials recorded by the evaluator. Documentation is not exhaustive; only key findings or relevant moments were captured.

### Application Packages

| Folder | Description |
|---------|--------------|
| `apps/hardened/` | Hardened Android application version with **SSL Pinning**, plus additional runtime protections such as **Integrity Verification**, **Anti-Hooking Detection**, and **Root Detection**. |
| `apps/not_hardened/` | Baseline Android application version that implements **SSL Pinning only**, without additional runtime protection mechanisms. |

## Purpose

This repository is part of the **Strutter Hardening Testing Research** project.  
It aims to ensure the **reproducibility** and **transparency** of the experimental results by providing:
- The actual tested Android application binaries.
- The participant testing data, including evaluator information and experiment outcomes.
- The detection methodology used in evaluating security mechanisms.

Researchers and practitioners can use this repository to replicate, validate, or extend this study.
