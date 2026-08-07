# Capstone Report — <your lane>

- **Author:** - Author: Eman Tariq
- **Lane:** -  Content Refresh Prioritization
- **Repo:** -  https://github.com/tariqeman727-ui/flyRank-Ai--internship
- **Date:** -  August 2026

> Copy this file to `work/capstone_report.md` and fill it in as you build. The eight
> sections mirror the Pass / Needs-Work rubric axes, so nothing here is optional.

## 1. Problem framing

This project supports the decision of prioritizing webpages that may benefit from content refresh.

Unit of analysis: One webpage (URL) in one month.

Output: A content refresh priority score and ranked list of pages.

Human action: Content teams can review the ranked pages and decide which pages should be updated.

Cost of a wrong call: Time may be wasted updating pages that do not need changes, or important improvement opportunities may be missed.

Machine learning helps because a large number of webpages cannot be manually reviewed efficiently. The model helps identify patterns in search performance signals and supports faster decision-making.

## 2. Data safety

The project used the FlyRank ML Internship Dataset (Hosted Release) with search performance and content-related features.

Used features:
- Clicks
- Impressions
- CTR
- Average Position
- Content performance signals

Excluded data:
- Private client names
- Private URLs
- Search queries containing sensitive information
- Production identifiers

Leakage checks:
- Future clicks were not used.
- Future impressions were not used.
- Future labels or outcomes were not used.
- Label-derived fields such as trend_direction and trend_pct were not used as model features.
- Pseudonymous IDs were only used for identification/grouping and not as predictive features.

No client-identifying information was included in the work folder.

## 3. Baseline

The transparent rule or score you built first. Why it's a fair comparison, and its numbers on
the same data and metric as your model.

## 4. Model / analysis

Your method and why it fits the lane. The exact feature list (and what you left out on
purpose). The target or proxy definition, in one sentence.

## 5. Evaluation

Your split (grouped by client? time-aware?) and why. Metrics, model vs baseline **on the same
split**. What the errors look like — a short error analysis beats a big metric table.

## 6. Interpretation

What the model/clusters actually found. Feature importances or cluster profiles in plain
words. Surprises and negative results — a well-understood "no effect" is a valid result.

## 7. Recommendation

The ranked actions or decisions your output supports, and how a FlyRank editor would use them
tomorrow. State your confidence and the limits explicitly.

## 8. Reproducibility

The exact commands to re-run everything from a fresh clone, your random seeds, and your
environment (`pip freeze` highlights or `requirements.txt` deltas).

---

> **Claims checklist before submitting:** observed / measured / directional / decision-support
> **Metrics vs. base rate:** report your task's base rate (majority-class %) next to any
> precision@K or accuracy — a high score can just be a high base rate. AUC / lift over
> baseline are the honest discrimination numbers.
> language everywhere · no causal claims without an experiment or causal design · no
> "predicted Google's algorithm" · no client-identifying details · numbers in this report
> match a fresh re-run.
