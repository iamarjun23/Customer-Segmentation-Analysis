# Customer Segmentation Analysis — RFM + Cohort

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Pandas](https://img.shields.io/badge/Pandas-2.0-green)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

## Business Problem

A D2C e-commerce business needed to understand which customers 
are most valuable, which are at risk of churning, and how 
retention varies across acquisition cohorts — to focus 
marketing spend and re-engagement campaigns on the right 
customer segments.

---

## Dataset

- **Rows:** 30,997 transactions (Jan 2022 – Dec 2023)
- **Columns:** order_id, customer_id, order_date, category, 
  quantity, unit_price, revenue, status, city
- **Unique customers:** 4,400

---

## Key Findings

| Finding | Detail | Business Impact |
|---|---|---|
| Revenue concentration | Top 20% of customers drive ~68% of total revenue | Pareto-based prioritisation — focus retention spend on Champions |
| Segment breakdown | Champions: 641 · At-Risk: 660 · Hibernating: 1,540 · New: 1,559 | Clear targeting strategy for each tier |
| Cohort retention | Month 1 retention drops to ~14% across most cohorts | Early-stage churn — re-engagement needed within 30 days |

---

## Customer Segments (RFM)

| Segment | Customers | Description | Recommended Action |
|---|---|---|---|
| Champions | 641 | High recency, high frequency | Loyalty programs, early access offers |
| At-Risk | 660 | Previously frequent, now declining recency | Targeted re-engagement — time-sensitive offers |
| Hibernating | 1,540 | Low recency, low frequency | Deprioritise — low ROI on marketing spend |
| New | 1,559 | Recent first-time buyers | Onboarding campaigns, second purchase incentives |

---

## Methodology

**RFM Scoring**
- Recency: Days since last purchase (lower = better → score 4)
- Frequency: Number of orders (higher = better → score 4)
- Monetary: Total spend (higher = better → score 4)
- Scoring method: Percentile-based binning (qcut)

**Cohort Analysis**
- Cohort defined by first purchase month
- Retention tracked by month-on-month repeat purchase rate
- Visualised as a heatmap showing decay curves per acquisition cohort

---

## Visualisations

| Chart | Insight |
|---|---|
| Customer segment distribution (bar) | Champions and At-Risk are close in size — At-Risk is critical to address |
| Revenue distribution by segment (boxplot) | Champions have highest median and range — confirms segment value |
| Cohort retention heatmap | Clear retention drop after month 1 across all cohorts |

---

## Tech Stack

| Layer | Tools |
|---|---|
| Data Processing | Python, Pandas, NumPy |
| Visualisation | Matplotlib, Seaborn |
| Environment | Jupyter Notebook |

---

## Project Structure

```
rfm-segmentation/
│
├── rfm_segmentation.ipynb    # Main analysis notebook
├── ecommerce_orders.csv      # Source dataset (30,997 rows)
├── rfm_output.csv            # RFM scores + segments export
└── README.md
```

---

## How to Run

```bash
git clone https://github.com/iamarjun23/rfm-segmentation
cd rfm-segmentation
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook rfm_segmentation.ipynb
```

---

## Business Recommendations

**1. Protect your Champions**
641 customers drive ~68% of revenue. Introduce a loyalty 
tier, early access to new products, and personalised 
communication. Losing even 10% of this segment has 
outsized revenue impact.

**2. Re-engage At-Risk customers immediately**
660 customers previously purchased frequently but recency 
is declining. Launch a time-sensitive win-back campaign 
within the next 30 days before they move to Hibernating.

**3. Focus on Month-1 retention**
Cohort analysis shows retention drops sharply after the 
first purchase. Implement an onboarding email sequence 
triggered within 7 days of first order to drive second 
purchases.

---

*Part of my Data Analyst portfolio → [github.com/iamarjun23](https://github.com/iamarjun23)*
