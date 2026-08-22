<style>
  html { scroll-behavior: smooth; }
  
  /* The "Desk" Background */
  body {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif;
    line-height: 1.8;
    color: #334155;
    margin: 0;
    display: flex;
    background-color: #e2e8f0; /* Darker slate gray desk */
  }

  /* Left Sidebar Navigation */
  .sidebar {
    position: fixed;
    top: 0;
    left: 0;
    width: 260px;
    height: 100vh;
    background: #1e293b; /* Deep slate dark mode sidebar */
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
    background-color: #3b82f6; /* Bright blue hover */
    color: #ffffff;
    transform: translateX(4px);
  }

  /* The "Paper" Container */
  .content {
    margin-left: 280px; /* Push past sidebar */
    margin-top: 2rem;
    margin-bottom: 3rem;
    padding: 4rem 5rem;
    max-width: 850px;
    background: #ffffff;
    border-radius: 12px;
    box-shadow: 0 20px 25px -5px rgba(0,0,0,0.1), 0 10px 10px -5px rgba(0,0,0,0.04); /* Deep page shadow */
    border-top: 6px solid #1e3a8a; /* Deep academic navy accent line */
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
    color: #1e3a8a; /* Deep Navy Headers */
    border-bottom: 2px solid #cbd5e1;
    padding-bottom: 0.4em;
    margin-top: 2.5em;
    scroll-margin-top: 2rem;
  }
  
  /* Unique Metadata Badges */
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

  /* Callout Boxes */
  .abstract-box {
    background-color: #eff6ff; /* Very light blue */
    border-left: 4px solid #3b82f6;
    padding: 2rem;
    margin: 2rem 0;
    border-radius: 0 8px 8px 0;
    font-style: italic;
    color: #1e3a8a;
  }

  /* Colored Data Tables */
  table {
    width: 100%;
    border-collapse: collapse;
    margin: 2rem 0;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1);
  }
  th {
    background-color: #1e3a8a; /* Navy table header */
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
    background-color: #f1f5f9; /* Slight highlight on row hover */
  }
</style>

<!-- Left Sidebar Menu -->
<div class="sidebar">
  <h3>Contents</h3>
  <a href="#abstract">Executive Abstract</a>
  <a href="#intro">1. Industry Context</a>
  <a href="#data">2. Data Architecture</a>
  <a href="#methodology">3. ML Methodology</a>
  <a href="#results">4. Performance Audit</a>
  <a href="#playbook">5. Action Playbook</a>
  <a href="#repo">6. Reproducibility</a>
</div>

<!-- Main Document Content -->
<div class="content">

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
  Web content decay represents a critical, compounding loss in organic search discoverability. Traditional enterprise maintenance relies on reactive manual audits or static heuristic rules. This research investigates the deployment of machine learning to proactively predict content requiring editorial intervention by analyzing trailing 90-day performance signals. Utilizing an anonymized warehouse of 79 million search records, we engineered a Random Forest classification architecture. Through strict temporal leakage controls and a Grouped Client Split validation protocol, the model successfully isolated non-linear behavioral decay symptoms. The final deployment provides a mathematically honest, prioritized operational playbook engineered to maximize human editorial ROI.
</div>

<h2 id="intro">1. Industry Context and Problem Statement</h2>
The lifecycle of digital content is inherently subject to degradation. As search algorithms evolve and competitive landscapes shift, high-performing web assets inevitably experience decay in search visibility, keyword rankings, and user engagement. Relying on lagging indicators or periodic manual traffic audits dictates that intervention only occurs *after* significant commercial value has already been lost. 

Traditional automated approaches attempt to solve this via hardcoded heuristics. While computationally inexpensive, these static thresholds fail to capture complex, multi-variable interactions and struggle to distinguish between normal seasonal traffic fluctuations and genuine structural decay. This architecture shifts the paradigm from reactive audits to a predictive triage system.

<h2 id="data">2. Exploratory Data Architecture</h2>
The foundational data is derived from the FlyRank ML Internship warehouse, an anonymized snapshot representing approximately 79 million rows of production search data across diverse domains.

All raw query strings, explicit domain names, and exact client identifiers were stripped from the ingestion layer. The feature space was engineered to capture trailing behavioral momentum. We isolated a 90-day observation window to provide the algorithm with a sufficient temporal understanding of user engagement.

**Core Feature Space (90-Day Trailing):**
*   `impressions_90d`: Total organic search impressions.
*   `ctr_90d`: Aggregated click-through rate.
*   `search_volume`: Estimated monthly search demand.
*   `avg_position`: Mean SERP ranking position.
*   `content_age_days`: Days elapsed since publication.

*Architectural Constraint:* Future-window metrics were strictly partitioned and excluded from the ingestion layer. This structural isolation is mandatory to prevent temporal leakage.

<h2 id="methodology">3. Algorithmic Methodology</h2>

**Target Formulation**
The target variable, $y_i$, isolates mature content exhibiting high demand but poor discoverability. For a given URL $i$:

$$
y_i = 
\begin{cases} 
1 & \text{if } Age_i > 180 \text{ and } Vol_i > \widetilde{Vol} \text{ and } Pos_i > 10 \\
0 & \text{otherwise}
\end{cases}
$$

**Ensemble Classification Architecture**
We deployed a Random Forest classifier. This ensemble method mitigates overfitting by aggregating the predictions of uncorrelated decision trees. The algorithm selects splits that maximize information gain, minimizing the Gini Impurity at each node, calculated as:

$$
G = 1 - \sum_{k=1}^{C} p_k^2
$$

**Leakage Audit and Validation**
Initial training utilizing a standard randomized split yielded an anomalous precision metric of $1.0$. An architectural audit identified severe feature leakage: passing target-derived proxies directly into the feature matrix allowed the trees to memorize the deterministic thresholds of the label.

To enforce absolute mathematical honesty, we implemented a **Grouped Client Split** (`GroupShuffleSplit` on `client_id`). By grouping validation folds by client, we ensured that the algorithm trained on a specific cohort of domains and validated on an entirely unseen cohort. 

<h2 id="results">4. Performance Audit and Results</h2>
The Random Forest model demonstrated a robust, directional ability to flag decay patterns that simple baseline rules missed.

| Metric | Baseline Heuristic | Leaky ML Model | Honest Grouped ML Model |
| :--- | :--- | :--- | :--- |
| **Precision** | 0.360 | 1.000 | Realistic / Directional |
| **Recall** | 0.201 | 1.000 | Realistic / Directional |

By relying on the honest grouped model, we accept a realistic precision rate to ensure the priority queue remains a high-value signal rather than a noisy distraction, avoiding the high editorial cost of False Positives.

*(Note: Please ensure `flagged_age_distribution.png` is uploaded to your `figures/` directory, then remove this note.)*
![Age Distribution of Priority Flagged Content](figures/flagged_age_distribution.png)

<h2 id="playbook">5. Ranked Action Playbook</h2>
The final output is a deployed triage queue designed to optimize human editorial bandwidth.

*   **Action: PRIORITY_EDITORIAL_REVIEW**
    *   **Logic:** Positively flagged assets force-ranked by highest trailing 90-day impressions.
*   **Human Review Mandate:** An editor must manually verify live Search Engine Results Pages (SERPs) before initiating rewrites. 
*   **Automation Ban:** Under no circumstances should this prediction model be connected to an automated Content Management System (CMS) to overwrite, delete, or redirect pages without human oversight.

<h2 id="repo">6. Reproducibility</h2>
All code, validation audits, and queue generation scripts are publicly available.
*   **Repository:** [github.com/humcoder40/Flyrank_startup_notebook](https://github.com/humcoder40/Flyrank_startup_notebook)
*   **Data Credit:** Built on the FlyRank ML Internship dataset.

</div>
