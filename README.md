# Proptech Conversion Friction Analysis
### A product data analysis project — tokenised real estate investment platform (UAE)

🔗 **[View the live interactive dashboard →](https://ajayprashant.github.io/proptech-conversion-analysis/dashboard.html)**

---

## Why I Built This

While exploring a UAE tokenised real estate platform as a prospective investor, I noticed a tension in the listing experience: a comprehensive document suite builds trust, but for first-time investors it likely creates the opposite effect — overwhelm and drop-off before a decision is ever made. This project tests that hypothesis end-to-end, using simulated but behaviourally grounded data, full funnel analysis, statistical testing, customer psychology, and a phased product recommendation with an A/B test design attached.

---

## The Business Problem

A UAE-based tokenised real estate platform has seen **+34% QoQ growth** in listing page views, but funded-listing conversion has **plateaued at 2.7%** against an internal Q3 target of 3%.

This project diagnoses *why* — using simulated but behaviourally realistic user data across 3,000 investors and 16,000+ funnel events.

---

## Deliverables

### 1. `proptech_conversion_analysis.ipynb`
Full Jupyter notebook covering:
- EDA — user composition, device split, KYC status
- Funnel analysis — stage-by-stage drop-off, segmented by investor type and device
- Document engagement analysis — correlation between doc behaviour and conversion
- Statistical significance testing (chi-square, Mann-Whitney U)
- Customer psychology layer — overchoice effect, dunning-kruger exit, mobile context mismatch
- A/B test design — hypothesis, sample size calculation (power analysis), guardrail metrics

### 2. `dashboard.html`
Interactive stakeholder dashboard with:
- Funnel table with live segment toggle (investor type / device type)
- Document engagement vs conversion analysis
- Customer psychology cards
- Phase-gated recommendation
- Full A/B test design

---

## Key Findings

| Finding | Metric |
|---------|--------|
| Biggest single drop-off | Listing Detail View → Document Engagement: **44.0%** |
| Document openers convert at | **5.5%** vs **0.2%** for non-openers — a **27× lift** |
| Engagement depth predicts conversion | 0 docs → 0.2% conversion; 4+ docs → **9.4%** conversion |
| Document type conversion range | 6.7%–7.5% — narrow range; depth matters more than which document |
| Mobile vs Desktop conversion | 1.0% vs 2.5% |
| First-time vs Returning investor conversion | 0.3% vs 3.4% |

---

## Recommendation

**Phase 1 (immediate, zero compliance risk):** Guided Document Hierarchy  
Surface one document first with a "Start Here" prompt, add plain-English doc labels, introduce a mobile-optimised reading mode, and show a Key Numbers card using structured data already in the DB. The data shows opening *any* first document is the activation trigger — not which one.

**Phase 2 (Q2):** Structured data layer — listing comparison, yield calculator  
**Phase 3 (Q3+, post-compliance review):** AI document Q&A

---

## Running the Notebook

```bash
pip install pandas numpy scipy matplotlib seaborn scikit-learn nbformat jupyter

# Generate data
python generate_data.py

# Open notebook
jupyter notebook proptech_conversion_analysis.ipynb
```

---

## Data Notes

Dataset is **simulated** with deliberately realistic noise — per-user conversion propensity (beta-distributed), listing-level demand variation, channel trust effects, and a small population of off-platform converters who invest without formal on-platform document engagement. Conversion rates and segment distributions are grounded in published benchmarks for regional fintech/proptech platforms. The methodology is production-applicable to real platform data.

---

*Analyst: Ajay Prashant*
