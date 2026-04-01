# Wahoo Fitness — Customer Segmentation Analysis

K-means clustering of 1,313 Wahoo Fitness customers to identify actionable psychographic and behavioral segments for targeted marketing and product strategy.

---

## Overview

Wahoo Fitness designs GPS cycling computers, running watches, and smart trainers for endurance athletes. As the brand's user base diversifies, a one-size-fits-all marketing approach loses effectiveness. This analysis segments Wahoo customers into **three distinct psychographic and behavioral profiles** using K-means clustering on survey data, enabling tailored product messaging, feature prioritization, and customer retention strategies.

**Dataset:** 1,313 survey respondents · 77 features · K = 3 clusters

---

## Key Findings

Three customer segments emerged from the clustering analysis:

| Segment | Profile |
|---------|---------|
| **Casual Cyclist** | Indoor cycling focus; price-sensitive; low equipment investment; does not engage with performance data — not Wahoo's target customer |
| **Dedicated Cyclist** | Outdoor cycling specialist; knowledgeable; owns GPS cycling computers and bike trainers; data-driven — high CLV |
| **Multi-Sport Athlete** | Participates in cycling, running, and triathlon; premium equipment buyer; highest data engagement and least price-sensitive — highest CLV |

---

## Methodology

| Step | Description |
|------|-------------|
| 1. Feature selection | 30 variables: psychographic attitude scales (Q1, Q2), sports participation flags, and product/device feature usage (QS6, QS7) |
| 2. Preprocessing | Mean imputation for sparse survey items; `StandardScaler` normalization |
| 3. Cluster count selection | Elbow method + silhouette analysis converge on **k = 3** |
| 4. K-means clustering | `KMeans(n_clusters=3, random_state=42, n_init=10)` |
| 5. Validation | Overall silhouette score; PCA 2D projection of cluster separation |

---

## Data

| File | Description |
|------|-------------|
| `Case Study 4 - Supplemental Segmentation.xlsx` | Raw survey data (1,313 rows × 77 features) |
| `appendix_figures.csv` / `.xlsx` | Cluster summary table export |

**Feature categories:**
- **Demographics:** `AGE`, `hqAge`
- **Sports participation:** `hqRun`, `hqCycle`, `hqTri`
- **Psychographic attitudes:** `Q1_1`–`Q1_2`, `Q2_1`–`Q2_12` (Likert 1–5)
- **Product features used (QS6):** 11 binary indicators
- **Device/platform features (QS7):** 9 binary indicators

---

## Setup

```bash
pip install -r requirements.txt
jupyter notebook wahoo_fitness_segmentation.ipynb
```

Running the notebook generates visualizations saved to a `figures/` directory (auto-created on first run).

---

## Repository Structure

```
wahoo_fitness/
├── wahoo_fitness_segmentation.ipynb            # Main analysis notebook
├── Case Study 4 - Supplemental Segmentation.xlsx  # Survey data
├── requirements.txt                            # Python dependencies
├── appendix_figures.csv                        # Cluster summary export
├── appendix_figures.xlsx                       # Cluster summary export
├── case_study_3_mjohnson.docx                  # Original written report
└── figures/                                    # Generated visualizations (on run)
```

---

## Academic Context

Completed for **MARK 6580 — Customer Analytics** at Georgetown University's McDonough School of Business (MSBA program).
