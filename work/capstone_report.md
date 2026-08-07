# Capstone Report — <your lane>

- **Author:** Eman Tariq
- **Lane:** Content Refresh Prioritization
- **Repo:** https://github.com/tariqeman727-ui/flyRank-Ai--internship
- **Date:** August 2026

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

The baseline was a rule-based prioritization score created in Week 4.

The baseline ranked webpages using existing search/content performance signals such as CTR, content age, and performance patterns.

This baseline provides a simple and transparent comparison before applying the machine learning model.

For fair evaluation, the baseline and the Decision Tree model were compared using the same train/test split.

Baseline output:
- Ranked webpages by refresh priority.
- Assigned reason codes such as STALE_LOW_CTR.
- Recommended actions such as Refresh Content.

The baseline acts as a reference point to measure whether the ML approach provides a more structured prioritization method.

## 4. Model / analysis

The project used a Decision Tree model for the Content Refresh Prioritization lane.

The Decision Tree method was selected because it provides an interpretable ML approach that can identify patterns between search performance signals and refresh priority.

Features used:
- Clicks
- Impressions
- CTR
- Average Position

Features deliberately excluded:
- trend_direction
- trend_pct
- Future performance information
- Client identifiers

Target definition:
The target was the Content Refresh Priority Score used to rank webpages that may benefit from content updates.

The model was designed to support content prioritization decisions, not to predict search engine algorithms or guarantee ranking improvements.

## 5. Evaluation

The model was evaluated using an 80% training and 20% testing split.

The same split was used for both the Week 4 baseline and the Decision Tree model to ensure a fair comparison.

Evaluation approach:
- Training data: 80%
- Testing data: 20%
- Same validation setup for baseline and model comparison

Results:
Results: Results: The Decision Tree model was compared against the Week 4 baseline using the same evaluation setup.

Error analysis:
- The model may struggle with pages having mixed performance signals.
- It mainly depends on available search performance features.
- Results should be interpreted as decision-support evidence rather than perfect prediction.

The evaluation shows a structured ML approach for prioritization, while keeping claims directional and honest.


## 6. Interpretation

The model identified patterns in search performance signals that can help prioritize pages for content refresh.

Key observations:
- Pages with high impressions but lower CTR may represent optimization opportunities.
- Ranking position and click behavior provide useful signals for prioritization.
- The Decision Tree model provides a more structured approach compared with a simple rule-based baseline.

Feature interpretation:
- Clicks indicate current user engagement.
- Impressions show search visibility opportunities.
- CTR highlights pages where better titles or descriptions may improve performance.
- Average Position provides ranking context.

The results are directional and should be used as decision-support evidence. The model does not prove causation or predict search engine ranking algorithms.

## 7. Recommendation

The model output supports ranked content refresh decisions for content teams.

Recommended actions:

1. Refresh pages with high impressions but low CTR.
2. Update outdated content that shows declining performance.
3. Improve titles and meta descriptions to increase click opportunities.
4. Review keyword alignment and user intent.
5. Monitor page performance and retrain the approach when new data becomes available.

How a content team can use it:
A FlyRank editor can review the ranked pages, check the reason codes, and decide which updates are worth applying.

Confidence and limitations:
The recommendations provide directional decision-support based on observed search signals. Human review is required before making content changes. The model does not guarantee improved rankings or traffic.

## 8. Reproducibility

The project can be reproduced by following the notebooks in sequence from the GitHub repository.

Repository:
https://github.com/tariqeman727-ui/flyRank-Ai--internship

Project notebooks:

- w01_research_question.ipynb
- w02_ml_task_framing.ipynb
- w03_data_contract.ipynb
- w03_feature_leakage_check.ipynb
- w04_baseline_score.ipynb
- w04_signal_audit.ipynb
- w05_model.ipynb
- w06_validation_audit.ipynb
- w07_action_playbook.ipynb
- capstone.ipynb

Environment:
- Python environment used through Google Colab.
- Main libraries: pandas, scikit-learn, matplotlib.

Random seed:
Random seed: A fixed random state was used during modeling to support reproducibility.

Run process:
1. Open notebooks in order.
2. Run data preparation and feature steps.
3. Train the baseline and Decision Tree model.
4. Review evaluation results and exported recommendations.

---

> **Claims checklist before submitting:** observed / measured / directional / decision-support
> **Metrics vs. base rate:** report your task's base rate (majority-class %) next to any
> precision@K or accuracy — a high score can just be a high base rate. AUC / lift over
> baseline are the honest discrimination numbers.
> language everywhere · no causal claims without an experiment or causal design · no
> "predicted Google's algorithm" · no client-identifying details · numbers in this report
> match a fresh re-run.
