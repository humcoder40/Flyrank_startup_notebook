# Optimizing Content Refresh Priorities with Machine Learning

**Abstract**
Identifying decaying web content is traditionally a reactive, manual process. This research asks if machine learning can accurately predict content requiring editorial updates using trailing 90-day performance signals. We evaluated a Random Forest classifier against a hardcoded heuristic baseline. After correcting for feature leakage using a grouped client split, the model demonstrated superior identification of decay patterns. The resulting artifact is a ranked action playbook to optimize editorial bandwidth.

### 1. Introduction
Content decay results in compounding losses in search traffic. The objective is to identify pages experiencing behavioral decay symptoms—such as dropping click-through rates despite high demand—to prioritize updates effectively.

### 2. Data
We utilized an anonymized snapshot of search performance data. The dataset includes historical 90-day impressions, click-through rates (CTR), and content age. Future-window metrics were strictly excluded to prevent temporal leakage.

### 3. Methodology
We engineered a target for "decay" (high volume, poor rank, high age). A Random Forest Classifier was trained to predict this target. Validation utilized a grouped split by client ID to ensure the model generalizes to unseen environments rather than memorizing domain-specific trends. 

### 4. Results
The machine learning model outperformed rigid baseline rules. While an initial leaky model showed 1.0 precision, our honest grouped-split model—which removed target-derived features—provided a realistic, directional signal that captures non-linear feature interactions the hardcoded baseline missed.

### 5. Limitations
This model provides decision-support, not absolute truth. It detects behavioral symptoms but cannot diagnose root causes, such as unannounced Google algorithm updates or zero-click featured snippets.

### 6. Ranked Recommendations (Action Playbook)
* **PRIORITY_EDITORIAL_REVIEW:** Pages older than 180 days with above-median impressions and below-median CTR.
* **Human Review Rule:** Editors must manually verify the live search results before rewriting. No automated CMS overwrites should occur based on these scores.

### Acknowledgments
Built on the FlyRank ML Internship dataset: [https://flyrank.ai](https://flyrank.ai)
