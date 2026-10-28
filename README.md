# CSE303: Statistics for Data Science — Mini Project

### East West University | Department of Computer Science & Engineering
* **Course:** CSE303 — Statistics for Data Science (Summer 2026)
* **Section:** 6 | **Group:** 3
* **Instructor:** Dr. Nafis Sadeq, Assistant Professor, Department of CSE

---

## 📌 Project Overview
* **Project Title:** Project 2: Verified-Purchase Prediction and Review Trustworthiness
* **Dataset:** Rokomari.com Bangla Book Reviews & Metadata
* **Core Research Question:** *Can linguistic and behavioral signals distinguish verified from non-verified Bangla book reviews?*

### ⚠️ Ethical Framing Choice
Non-verified reviews are **not** automatically categorized as fake reviews. A non-verified review is not necessarily deceptive; many genuine readers purchase physical books offline (e.g., local bookstores, book fairs, libraries) and subsequently review the title on Rokomari.com. The task is strictly framed as **Purchase-Verification Prediction** and **Review Trustworthiness Analysis**.

---

## 👥 Group Members (Section 6, Group 3)

| Name | Student ID |
| :--- | :--- |
| **Mahadi Prodhan** | `2023-2-60-033` |
| **Rishad Imtinan** | `2023-3-60-014` |
| **Md Mahiruddin Chowdhury** | `2023-3-60-504` |

---

## 🔬 Key Methodology & Findings

1. **Data Deduplication & Preprocessing:**
   * Removed 538,386 duplicate review instances (72.33%) to guarantee statistical independence of observations.
   * Engineered 20 features (6 continuous + 13 categorical one-hot encoded categories + 1 bias unit).
   * Applied Min-Max normalization and $\log(1+x)$ scaling to correct heavy text length skewness.

2. **Statistical Hypothesis Testing:**
   * **Two-Sample Z-Test for Proportions:** Significant rating bias found ($Z = -15.53, p < 0.001$). Non-verified reviews display higher 5-star rates (69.71% vs 62.55%).
   * **Welch’s Two-Sample Independent T-Test:** Non-verified reviews are significantly longer ($T = -41.15, p < 0.001$).
   * **One-Way ANOVA across Book Categories:** Significant cross-genre variance ($F = 115.94, p < 0.001$).

3. **Machine Learning & Threshold Calibration:**
   * Custom L2-regularized logistic regression with optimal hyperparameters ($\alpha^* = 0.10, \lambda^* = 0.00$).
   * Calibrated decision threshold from default $T = 0.50$ to validation median $T^* = 0.5899$.
   * **Result:** Specificity surged from 14.13% to **64.26%** (+50.13% gain), Precision reached **69.73%**, and Balanced Error Rate dropped to **38.34%**.

---

## 📂 Repository Structure

```text
CSE303/
├── README.md                                # Course and project documentation
├── code/
│   └── CSE303_Group3_Sec6_Project.ipynb     # Complete data analysis, statistical tests & model code
├── slide/
│   └── Presentation Slides PDF.pdf          # Final presentation slides
└── report/
    └── CSE303 Group3 Section 6 Project Report.pdf  # Comprehensive academic research report
```
