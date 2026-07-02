# Diwali Sales Analysis — Business Report

**Prepared for:** Leadership · Marketing · Category · CRM  
**Data window:** Single Diwali festive campaign  
**Records analysed:** 11,231 cleaned transactions (from 11,251 raw)  
**Currency:** INR (₹)

---

## 1. Executive Summary

The Diwali campaign generated approximately **₹10.6 Cr** in revenue over **11,231 transactions** from **~10.9k unique customers**, at an average ticket size of **~₹9,450**. Growth is not evenly distributed — it is concentrated in **five states**, **two zones**, **three categories** and a **married-female 26–35 persona**. The single highest-leverage action for the next Diwali cycle is to **re-orient marketing, inventory and CRM around this persona**, while running dedicated programmes for two smaller-but-critical customer tiers: **VIP Champions** and **Loyal High-Spenders**.

## 2. Business Context

Diwali is India's largest retail moment. Marketing spend, inventory pre-positioning and CRM offers must be planned in advance, but leadership currently lacks a single, evidence-based view of *who* buys, *where*, and *what*. This report converts raw transactions into a persona-led festive strategy.

## 3. Methodology

- **Data cleaning** — dropped two fully-null columns, removed 12 revenue-null rows, cast dtypes, snake-cased columns, engineered `avg_order_value` and `revenue_bucket`.
- **Descriptive analysis** — 20+ visualisations across gender, age group, marital status, state, zone, occupation, category and customer levels.
- **Statistical tests** — Welch's t-test on gender × amount; one-way ANOVA on amount × age group. Both confirmed the qualitative story with p < 0.05.
- **Outlier detection** — IQR method; ~1–2% outliers, all premium buyers (kept in-sample).
- **Segmentation** — K-Means (k = 4) on `frequency`, `monetary`, `AOV` after standardisation. Elbow method confirmed k = 4.

## 4. Key Findings

### 4.1 Demographics
- **Female buyers** contribute **>65%** of both volume and revenue.
- The **26–35** cohort is the single largest revenue engine across every zone.
- **Married buyers** contribute the majority of revenue — household gifting is the true festive tailwind.

### 4.2 Geography
- **Top-5 states by revenue:** Uttar Pradesh, Maharashtra, Karnataka, Delhi, Madhya Pradesh.
- **Zone leaders:** Central and Southern zones together generate over **55%** of national revenue.
- **Under-indexed:** Eastern zone shows below-average revenue and orders — an expansion opportunity.

### 4.3 Occupation
- **IT, Healthcare, Aviation** professionals lead in per-capita spend.
- **Retail and Agriculture** underperform on AOV — value-tier products likely resonate better here.

### 4.4 Products
- **Volume champions:** Food, Clothing & Apparel, Electronics — never allow stockouts.
- **Highest AOV:** Electronics — bundle offers here have the greatest revenue impact.
- **Long-tail:** Veterinary, Office, Pet Care — small but consistent; ideal for niche affinity campaigns.

### 4.5 Customer Segmentation (K-Means)

| Segment | Approx. size | Behaviour | CRM playbook |
|---|---|---|---|
| **VIP / Champions** | ~5–10% | Very high monetary + AOV | Concierge, early access, personalised gifting |
| **Loyal High-Spenders** | ~20–25% | High monetary, mid frequency | Bundle offers, referral incentives, cross-sell |
| **Regulars** | ~40–45% | Median spend, median frequency | AOV nudges, free-shipping thresholds |
| **Bargain / Low-Value** | ~25–30% | Low monetary, low frequency | Coupons, reactivation combos |

## 5. Business Questions Answered

- **Who generates the highest revenue?** A small VIP tier plus married female buyers aged 26–35 in the IT / Healthcare / Aviation occupations.
- **Which customer segments should marketing target?** Primarily *Loyal High-Spenders* (largest revenue block after VIPs) and the *Regulars* who are one nudge away from becoming Loyals.
- **Which states require more marketing investment?** The Eastern zone at large (Bihar, Jharkhand), plus growth markets like Kerala and Punjab that under-index relative to their income base.
- **Which product categories drive maximum revenue?** Food and Clothing lead volume; Electronics leads AOV — invest in *all three* for compounded impact.
- **Which demographics have the highest purchasing power?** Married women 26–35 in the top-3 occupations named above.
- **What will increase festive-season sales?** See §6.

## 6. Recommendations

1. **Persona-first creative.** Build "Married Woman, 26–35, IT/Healthcare" as the primary campaign persona; regionalise for UP, MH, KA, DL, MP.
2. **Category strategy.** Guarantee stock on Food, Clothing and Electronics; run bundle offers to lift AOV in the ₹5–15K sweet spot.
3. **Geo strategy.** Pilot heavier ad spend in the under-penetrated Eastern zone with regional-language creatives.
4. **VIP retention.** Dedicated concierge tier, early-access hours and personalised gifting hampers.
5. **AOV nudges.** Free shipping threshold, "add-one-more" bundles and EMI tags on Electronics.
6. **Occupation targeting.** LinkedIn / programmatic layers focused on IT, Healthcare and Aviation.
7. **Cross-sell playbook.** Food + Decor bundles for households; Clothing + Beauty for women 26–35.

## 7. Risks & Assumptions

- Single-window dataset — no YoY comparison; assumptions on trend direction should be validated with next year's data.
- No return / refund column — headline revenue may over-state net revenue.
- No campaign / channel attribution — recommendations assume media flexibility.

## 8. Next Steps

1. Layer in multi-year Diwali data for true RFM and YoY.
2. Integrate web/app analytics for channel attribution.
3. Build a propensity-to-buy model for a 30-day pre-festive window.
4. Add profitability and return-rate columns to the fact table.
5. Automate the pipeline: raw CSV → cleaned parquet → scheduled Power BI refresh.

---

*Report generated as part of the Diwali Sales Analysis project. Companion assets: `notebooks/Diwali_Sales_Analysis.ipynb`, `powerbi/` build guide, `data/cleaned/Diwali_Sales_Cleaned.csv`.*
