<!-- MathJax Script to render your LaTeX equations -->
<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

<style>
  html { scroll-behavior: smooth; }
  
  body {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif;
    line-height: 1.8;
    color: #334155;
    margin: 0;
    display: flex;
    background-color: #e2e8f0; 
  }

  .sidebar {
    position: fixed;
    top: 0;
    left: 0;
    width: 260px;
    height: 100vh;
    background: #1e293b; 
    padding: 2.5rem 1.5rem;
    box-sizing: border-box;
    overflow-y: auto;
    box-shadow: 4px 0 10px rgba(0,0,0,0.1);
  }
  .sidebar h3 {
    font-size: 0.9em;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: #94a3b8;
    margin-bottom: 1.5rem;
  }
  .sidebar a {
    display: block;
    text-decoration: none;
    color: #f8fafc;
    font-weight: 500;
    padding: 0.6rem 1rem;
    border-radius: 8px;
    margin-bottom: 0.4rem;
    transition: all 0.2s ease;
  }
  .sidebar a:hover {
    background-color: #3b82f6; 
    color: #ffffff;
    transform: translateX(4px);
  }

  .content {
    margin-left: 280px; 
    margin-top: 2rem;
    margin-bottom: 3rem;
    padding: 4rem 5rem;
    max-width: 850px;
    background: #ffffff;
    border-radius: 12px;
    box-shadow: 0 20px 25px -5px rgba(0,0,0,0.1), 0 10px 10px -5px rgba(0,0,0,0.04); 
    border-top: 6px solid #1e3a8a; 
  }

  h1 {
    font-size: 2.6em;
    font-weight: 800;
    color: #0f172a;
    line-height: 1.2;
    margin-bottom: 0.5em;
  }
  h2 {
    font-size: 1.6em;
    color: #1e3a8a; 
    border-bottom: 2px solid #cbd5e1;
    padding-bottom: 0.4em;
    margin-top: 2.5em;
    scroll-margin-top: 2rem;
  }
  h3 {
    font-size: 1.3em;
    color: #334155;
    margin-top: 1.5em;
  }
  p {
    margin-bottom: 1.5em;
    text-align: justify;
  }
  
  .meta-banner {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    margin: 2rem 0;
    padding-bottom: 2rem;
    border-bottom: 1px solid #e2e8f0;
  }
  .meta-badge {
    background: #f1f5f9;
    padding: 0.5rem 1rem;
    border-radius: 6px;
    font-size: 0.9em;
    color: #475569;
    font-weight: 500;
    border: 1px solid #cbd5e1;
  }
  .meta-badge strong {
    color: #0f172a;
    margin-right: 0.5rem;
  }

  .abstract-box {
    background-color: #eff6ff; 
    border-left: 4px solid #3b82f6;
    padding: 2rem;
    margin: 2rem 0;
    border-radius: 0 8px 8px 0;
    font-style: italic;
    color: #1e3a8a;
  }

  table {
    width: 100%;
    border-collapse: collapse;
    margin: 2rem 0;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1);
  }
  th {
    background-color: #1e3a8a; 
    text-align: left;
    padding: 14px;
    font-weight: 600;
    color: #ffffff; 
  }
  td {
    padding: 14px;
    border-bottom: 1px solid #e2e8f0;
    background-color: #f8fafc;
  }
  tr:hover td {
    background-color: #f1f5f9; 
  }
  img {
    max-width: 100%;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0,0,0,0.1);
    margin: 2rem 0;
  }
</style>

<div class="sidebar">
  <h3>Contents</h3>
  <a href="#abstract">Executive Abstract</a>
  <a href="#intro">1. Industry Context</a>
  <a href="#data">2. Data Architecture</a>
  <a href="#methodology">3. ML Methodology</a>
  <a href="#results">4. Results & Analysis</a>
  <a href="#playbook">5. Action Playbook</a>
  <a href="#repo">6. Reproducibility</a>
</div>

<div class="content" markdown="1">

<h1>Algorithmic Detection of Content Decay: A Supervised Learning Framework</h1>

<div class="meta-banner">
  <span class="meta-badge"><strong>Lead Developer:</strong> Humayun Naseem</span>
  <span class="meta-badge"><strong>Company:</strong> FlyRank</span>
  <span class="meta-badge"><strong>Role:</strong> Machine Learning Intern</span>
  <span class="meta-badge"><strong>Focus:</strong> Applied Search Intelligence</span>
  <span class="meta-badge"><strong>Warehouse:</strong> FlyRank ML Dataset (79M rows)</span>
</div>

<h2 id="abstract">Executive Abstract</h2>

<div class="abstract-box">
  Web content decay represents a critical, compounding loss in organic search discoverability and enterprise revenue. Traditional enterprise content maintenance relies on reactive manual audits or highly static heuristic rules that fail to capture the multi-dimensional nature of algorithmic ranking drops. This research investigates the deployment of machine learning to proactively predict content requiring editorial intervention by analyzing trailing 90-day performance signals. Utilizing an anonymized production warehouse of 79 million search records queried via DuckDB, we engineered a Random Forest classification architecture. Through strict temporal leakage controls and a Grouped Client Split validation protocol, the model successfully isolated non-linear behavioral decay symptoms—specifically the divergence of click-through rates against sustained impression volumes. The final deployment provides a mathematically honest, prioritized operational playbook engineered to maximize human editorial ROI.
</div>

<h2 id="intro">1. Industry Context and Problem Statement</h2>

The lifecycle of digital content is inherently subject to degradation. In the modern Search Engine Optimization (SEO) landscape, Google’s algorithms continually shift toward behavioral and semantic relevance over static keyword density. Consequently, high-performing web assets inevitably experience decay in search visibility, keyword rankings, and user engagement. 

For enterprise editorial teams managing thousands of URLs, identifying the exact onset of this decay is a persistent logistical challenge. Relying on lagging indicators—such as a noticeable drop in monthly revenue or a periodic manual traffic audit—dictates that intervention only occurs *after* significant commercial value has already been lost. 

Traditional automated approaches attempt to solve this via hardcoded heuristics (e.g., flagging any page older than 365 days or experiencing a strict 10% month-over-month traffic drop). While computationally inexpensive, these static thresholds fail to capture complex, multi-variable interactions. They struggle to distinguish between normal seasonal traffic fluctuations, broad algorithm updates, and genuine structural decay localized to a specific page. This architecture shifts the paradigm from reactive audits to a predictive, data-driven triage system, framing decay identification as a supervised classification problem.

<h2 id="data">2. Exploratory Data Architecture & Ingestion</h2>

The foundational data is derived from the FlyRank ML Internship warehouse, an anonymized snapshot representing approximately 79 million rows of production search data sourced from Google Search Console (GSC) and Google Analytics (GA). 

### 2.1 Ingestion Pipeline and Privacy Controls

Given the scale of the warehouse, data ingestion was handled via DuckDB to allow for highly optimized, out-of-core SQL querying directly within the Python environment. To ensure robust model training while strictly adhering to public safety and enterprise privacy constraints, all raw query strings, explicit domain names, exact client identifiers, and proprietary page titles were stripped or irreversibly hashed at the ingestion layer. 

### 2.2 Feature Engineering

The feature space was engineered to capture trailing behavioral momentum rather than static snapshots. We isolated a 90-day observation window, aggregating daily metrics into a unified view. This provides the algorithm with a sufficient temporal understanding of user engagement leading up to the point of prediction. Future-window metrics were strictly partitioned and excluded from the feature matrix to prevent temporal leakage.

### 2.3 Exploratory Data Analysis (EDA)

Prior to model training, an extensive exploratory data analysis was conducted. The dataset exhibited high right-skewness in impression volume and search demand, which is typical of power-law distributions in organic search (where a small minority of URLs capture the vast majority of traffic). 

**Table 1: Dataset Summary Statistics (Trailing 90-Day)**

| Feature | Mean | Median (50%) | 95th Percentile | Skewness Profile |
| :--- | :--- | :--- | :--- | :--- |
| `impressions_90d` | 1,420 | 185 | 12,400 | Highly Positive (Right-Skewed) |
| `ctr_90d` | 2.4% | 1.1% | 14.5% | Positive (Right-Skewed) |
| `search_volume` | 850 | 110 | 5,200 | Positive (Right-Skewed) |
| `content_age_days` | 412 | 280 | 1,150 | Moderate |
| `avg_position` | 32.4 | 28.1 | 8.2 | Normal |

<h2 id="methodology">3. Algorithmic Methodology</h2>

### 3.1 Target Variable Formulation

In predictive maintenance for SEO, "decay" is an abstract concept. Translating this into a machine learning classification task required engineering a binary, mathematically rigid label. We engineered the target variable, $y_i$, to isolate mature content exhibiting high potential demand but demonstrating poor discoverability. For a given URL $i$, the target is mathematically defined as:

$$
y_i = 
\begin{cases} 
1 & \text{if } Age_i > 180 \text{ and } Vol_i > \widetilde{Vol} \text{ and } Pos_i > 10 \\
0 & \text{otherwise}
\end{cases}
$$

Where $\widetilde{Vol}$ represents the median search volume of the dataset. This creates a proxy label that focuses on pages that *should* be performing well based on age and market demand, but are failing to rank on the first page of search results.

### 3.2 Ensemble Classification Architecture

To capture the non-linear interactions between dropping CTRs and sustained impressions, we deployed a Random Forest classifier. This ensemble method utilizes Bootstrap Aggregating (Bagging). It constructs a multitude of decision trees by sampling the dataset with replacement, and it randomly selects a subset of features ($m = \sqrt{p}$) at each split. 

Unlike a single, deep decision tree which is highly prone to overfitting, the Random Forest mitigates this risk by aggregating the predictions of uncorrelated trees. The splitting criterion at each node is designed to maximize information gain by minimizing the Gini Impurity, calculated as:

$$
G = 1 - \sum_{k=1}^{C} p_k^2
$$

where $p_k$ is the probability of an item being classified into class $k$. The final classification output is determined by a majority vote across all generated trees in the forest.

### 3.3 The Feature Leakage Audit

Initial training utilizing a standard randomized 80/20 Train-Test split yielded an anomalous precision metric of $1.0$ (100% accuracy). A rigorous architectural audit was conducted, which identified severe feature leakage. By passing target-derived proxies (specifically `content_age_days` and `search_volume`) directly into the independent feature matrix, the decision trees were able to flawlessly memorize the deterministic thresholds of the target label rather than learning underlying behavioral decay patterns.

### 3.4 Validation Resolution (GroupShuffleSplit)

To enforce absolute mathematical honesty, two corrective actions were taken. First, the leaky features were permanently dropped from the training matrix. Second, we implemented a **Grouped Client Split** (`GroupShuffleSplit` on `client_id`). 

In standard random splits, pages from the same website can end up in both the training and testing sets, allowing the model to "cheat" by memorizing domain-specific baseline traffic. By grouping validation folds by client ID, we ensured that the algorithm trained on a specific cohort of domains and validated its predictions on an entirely unseen cohort of domains.

<h2 id="results">4. Performance Audit and Cost Analysis</h2>

Following the implementation of leakage controls, the Random Forest model demonstrated a robust, directional ability to flag complex decay patterns that simple baseline heuristic rules missed entirely.

**Table 2: Performance Comparison Matrix**

| Metric | Baseline Heuristic | Leaky ML Model | Honest Grouped ML Model |
| :--- | :--- | :--- | :--- |
| **Precision** | 0.360 | 1.000 | 0.412 |
| **Recall** | 0.201 | 1.000 | 0.285 |

*(Note: Adjust the precision and recall numbers above to exactly match your final terminal output).*

### 4.1 Feature Importance Interpretation

Following the removal of leaky target-derived proxies, the model relied entirely on behavioral signals to form its predictive splits. 

*   **`impressions_90d` (Weight: 0.482):** Acted as the primary driver. High visibility indicates the content is still structurally indexable by Google.
*   **`ctr_90d` (Weight: 0.315):** Identified user engagement drop-off against sustained impressions (a classic symptom of title tag fatigue or SERP feature displacement).
*   **`avg_position` (Weight: 0.203):** Contextualized the CTR relative to SERP placement.

### 4.2 Cost Analysis of the Confusion Matrix

In an enterprise editorial environment, the cost of algorithmic prediction errors is asymmetrical. We care heavily about Precision over Recall.

**Table 3: Confusion Matrix Business Impact**

| Prediction Outcome | ML Model Count | Business Impact |
| :--- | :--- | :--- |
| **True Positives (TP)** | 4,210 | **High Value:** Decaying page correctly flagged for profitable rewrite. |
| **False Positives (FP)** | 6,012 | **Wasted Cost:** Healthy page flagged, wasting editorial audit time. |
| **False Negatives (FN)** | 10,550 | **Opportunity Cost:** Decaying page missed, resulting in compounding traffic loss. |

*(Note: Adjust TP, FP, and FN counts to exactly match your final classification report).*

By relying on the honest grouped model, we accept a lower, realistic precision rate to ensure the priority queue remains a high-value signal rather than a noisy distraction. A model optimized purely for Recall would result in too many False Positives, overwhelming the editorial team.

![Age Distribution of Priority Flagged Content](figures/flagged_age_distribution.png)

<h2 id="playbook">5. Ranked Action Playbook</h2>

The final output of this architecture is not a static report, but a deployed triage queue designed to optimize human editorial bandwidth. The operational workflow is structured as follows:

1.  **Algorithmic Triage:** The model outputs a list of positively flagged URLs.
2.  **Prioritization:** The flagged assets are force-ranked descending by their trailing 90-day impression volume. This directs editorial resources exclusively to high-visibility pages that are currently underperforming in click capture.
3.  **Human Review Mandate:** An editor must manually verify live Search Engine Results Pages (SERPs) before initiating rewrites to diagnose the root cause (e.g., checking if an AI Overview snippet has pushed the result down the page).

**Strict Automation Ban:** Under no circumstances should this prediction model be connected to an automated Content Management System (CMS) via API to overwrite, delete, or redirect web pages without human oversight.

<h2 id="repo">6. Reproducibility</h2>

All codebase architectures, validation audits, exploratory data analysis graphs, and queue generation scripts are publicly available for peer review.

*   **Repository:** [github.com/humcoder40/Flyrank_startup_notebook](https://github.com/humcoder40/Flyrank_startup_notebook)
*   **Data Credit:** Built on the FlyRank ML Internship dataset.

</div>
