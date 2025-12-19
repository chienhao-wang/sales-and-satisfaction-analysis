# Store Strategy Experimentation  
### A Controlled A/B Test with Difference-in-Differences Analysis

![Status](https://img.shields.io/badge/Status-Project_Completed-success)
![Python](https://img.shields.io/badge/Python-Machine_Learning-3776AB?style=flat&logo=python&logoColor=white)

---
## Table of Contents

- [Business Objective](#1-business-objective)
- [Problem Framing](#2-problem-framing)
- [Analytical Approach](#3-analytical-approach)
- [Experiment Validation & Readiness](#4-experiment-validation--readiness)
- [Revenue Impact Analysis (Sales)](#5-revenue-impact-analysis-sales)
- [Customer Satisfaction Impact](#6-customer-satisfaction-impact)
- [Segment-Level Impact Analysis (Sales & Satisfaction)](#7-segment-level-impact-analysis-sales--satisfaction)
- [Key Findings](#8-key-findings)
- [Limitations & Next Steps](#9-limitations--next-steps)

---

## 1. Business Objective
Evaluate whether a newly introduced store strategy drives incremental
sales growth without negatively impacting customer satisfaction, using
a controlled experiment.

---

## 2. Problem Framing
Before rolling out the new strategy at scale, management requires **causal evidence** of its effectiveness. 
Simple observational comparisons are insufficient due to potential baseline differences between stores or customers.

A randomised Control vs Treatment experiment was therefore designed to enable robust causal inference.

---

## 3. Analytical Approach
The analysis follows a structured experimental framework:

- Randomised Control vs Treatment design
- Sanity checks for experiment validity:
  - Sample Ratio Mismatch (SRM)
  - Pre-experiment balance tests
  - Statistical power and minimum detectable effect (MDE)
- Post-experiment comparison of key outcomes
- Difference-in-Differences (DID) estimation for causal impact
- Visual validation using interaction plots

---

## 4. Experiment Validation & Readiness

### 4.1 Randomisation & Balance Checks
Control (5,013) and Treatment (4,987) groups are well balanced, with no evidence of sample ratio mismatch.

Pre-experiment sales and customer satisfaction metrics show no statistically significant differences between groups, confirming comparability prior to intervention (*p-value = 0.1375*).

### Table 1: Pre-Experiment Means

| Metric                         | Control    | Treatment  | Difference (Control − Treatment) |
|--------------------------------|------------|------------|----------------------------------|
| Sales Before ($)               | 203.03     | 204.67     | -1.65                            |
| Customer Satisfaction Before   | 70.48      | 70.02      | 0.47                             |


### 4.2 Power Analysis
The experiment is sufficiently powered to detect a minimum sales difference of **$3.11 per customer** at 80% power, ensuring sensitivity to economically meaningful effects.

**Conclusion:**  
The experimental design is statistically robust and suitable for causal decision-making (see Figure 1).

<p align="left">
  <img src="sales_before_distribution.png" width="900">
  <br>
  <em>Figure 1: Distribution Sales Before Experiment (Treatment vs. Control)</em>
</p>

---

## 5. Revenue Impact Analysis (Sales)

### 5.1 Post-Experiment Comparison
- Average Sales (Control): **$242.83**
- Average Sales (Treatment): **$318.13**
- Simple uplift: **+31.0%** (p < 0.001)

### 5.2 Causal Impact (Difference-in-Differences)
Using a DID framework to control for baseline effects:

- Incremental sales uplift: **+$73.65 per customer**
- Statistical significance: **p < 0.001**

**Conclusion:**  
Sales trends diverge clearly after intervention, with Treatment outperforming Control (see Figure 2). The new store strategy delivers a statistically significant and economically material increase in revenue, with strong causal evidence.

<p align="left">
  <img src="did_sales_plot.png" width="900">
  <br>
  <em>Figure 2: Difference-in-Differences: Sales Impact</em>
</p>

---

## 6. Customer Satisfaction Impact

A Difference-in-Differences analysis was also applied to customer satisfaction scores to assess potential trade-offs between revenue and customer experience.

- Average Satisfaction (Control): **74.15**
- Average satisfaction (Treatment): **73.69**
- Net DID effect: **+0.01 points**
- Statistical significance: **Not significant (p = 0.96)**

**Conclusion:**  
Satisfaction trends remain parallel across groups (See Figure 3). Revenue gains are achieved **without compromising customer satisfaction**.

<p align="left">
  <img src="did_sat_plot.png" width="900">
  <br>
  <em>Figure 3: Difference-in-Differences: satisfaction Impact</em>
</p>

---

## 7. Segment-Level Impact Analysis (Sales & Satisfaction)

To understand whether the store strategy performs differently across customer types, a segmented Difference-in-Differences (DID) analysis was conducted for **High-, Medium-, and Low-Value customers**.

### Sales Impact by Segment  
| Customer Segment | DID Uplift ($) | Relative Lift (%) | Statistical Significance |
|------------------|---------------|-------------------|--------------------------|
| High Value       | +81.28        | +30.4%            | Significant              |
| Medium Value     | +73.61        | +30.3%            | Significant              |
| Low Value        | +66.39        | +30.5%            | Significant              |

The strategy delivers a **consistent relative uplift (~30%) across all segments**, with the **largest absolute revenue gain driven by High-Value customers**.

<p align="left">
  <img src="segment_sales_analysis.png" width="900">
  <br>
  <em>Figure 4: Average Sales After by Customer Segment and Group</em>
</p>

### Customer Satisfaction Impact by Segment
No statistically significant changes in customer satisfaction are observed across any segment, indicating that the revenue uplift does not come at the expense of customer experience.

### Segment-Level Conclusion
While the strategy is effective across all customer segments, the **highest absolute ROI is achieved among High-Value customers**.
This suggests that an initial rollout prioritising high-value segments would maximise short-term revenue impact, with broader rollout to other segments remaining low risk.

---

## 8. Key Findings
- The experiment is well-randomised, balanced, and statistically sound
- The store strategy generates a **causal sales uplift of $73.65 per customer**
- No negative impact on customer satisfaction is observed
- Results are both statistically significant and commercially relevant

---

## 9. Limitations & Next Steps
- The experiment captures short-term effects only
- Results may vary across store size, region, or customer segments

**Next steps:**
- Longer observation window to assess sustainability
- Follow-up experiments to optimise specific strategy components

---

## 10. Tools & Methods
- Python (pandas, scipy, statsmodels)
- Statistical hypothesis testing
- Difference-in-Differences methodology
- Data visualisation with seaborn & matplotlib
