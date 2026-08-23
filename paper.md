<!-- MathJax Script for LaTeX Equations -->
<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

<style>
  html { scroll-behavior: smooth; }
  body { font-family: 'Inter', -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif; line-height: 1.8; color: #334155; margin: 0; display: flex; background-color: #e2e8f0; }
  
  /* Left Sidebar Navigation */
  .sidebar { position: fixed; top: 0; left: 0; width: 280px; height: 100vh; background: #1e293b; padding: 2.5rem 1.5rem; box-sizing: border-box; overflow-y: auto; box-shadow: 4px 0 10px rgba(0,0,0,0.1); }
  .sidebar h3 { font-size: 0.9em; text-transform: uppercase; letter-spacing: 0.1em; color: #94a3b8; margin-bottom: 1.5rem; }
  .sidebar a { display: block; text-decoration: none; color: #f8fafc; font-weight: 500; padding: 0.7rem 1rem; border-radius: 8px; margin-bottom: 0.5rem; transition: all 0.2s ease; font-size: 0.95em; }
  .sidebar a:hover { background-color: #3b82f6; color: #ffffff; transform: translateX(4px); }
  
  /* The "Paper" Container */
  .content { margin-left: 300px; margin-top: 2rem; margin-bottom: 4rem; padding: 5rem 6rem; max-width: 900px; background: #ffffff; border-radius: 12px; box-shadow: 0 20px 25px -5px rgba(0,0,0,0.1), 0 10px 10px -5px rgba(0,0,0,0.04); border-top: 6px solid #1e3a8a; }
  
  /* Typography */
  h1 { font-size: 2.8em; font-weight: 800; color: #0f172a; line-height: 1.25; margin-bottom: 0.5em; text-align: center; }
  h2 { font-size: 1.8em; color: #1e3a8a; border-bottom: 2px solid #cbd5e1; padding-bottom: 0.4em; margin-top: 2.5em; margin-bottom: 1em; scroll-margin-top: 2rem; }
  h3 { font-size: 1.4em; color: #334155; margin-top: 2em; margin-bottom: 1em; }
  p { margin-bottom: 1.5em; text-align: justify; font-size: 1.05em; color: #475569; }
  li { margin-bottom: 0.8em; text-align: justify; font-size: 1.05em; color: #475569; }
  
  /* Metadata Banners */
  .meta-banner { display: flex; flex-wrap: wrap; gap: 1rem; justify-content: center; margin: 3rem 0; padding-bottom: 3rem; border-bottom: 1px solid #e2e8f0; }
  .meta-badge { background: #f1f5f9; padding: 0.6rem 1.2rem; border-radius: 6px; font-size: 0.95em; color: #475569; font-weight: 500; border: 1px solid #cbd5e1; }
  .meta-badge strong { color: #0f172a; margin-right: 0.5rem; text-transform: uppercase; font-size: 0.85em; letter-spacing: 0.05em; }
  
  /* Callouts */
  .abstract-box { background-color: #eff6ff; border-left: 5px solid #3b82f6; padding: 2.5rem; margin: 3rem 0; border-radius: 0 12px 12px 0; font-style: italic; color: #1e3a8a; font-size: 1.1em; line-height: 1.8; }
  
  /* Tables */
  table { width: 100%; border-collapse: collapse; margin: 3rem 0; border-radius: 8px; overflow: hidden; box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1); }
  th { background-color: #1e3a8a; text-align: left; padding: 16px; font-weight: 600; color: #ffffff; font-size: 1.05em; }
  td { padding: 16px; border-bottom: 1px solid #e2e8f0; background-color: #f8fafc; font-family: 'Fira Code', monospace; font-size: 0.95em; color: #334155; }
  tr:hover td { background-color: #f1f5f9; }
  
  /* Custom Data Visualization Charts */
  .bar-chart-container { margin: 3rem 0; background: #ffffff; padding: 2rem; border: 1px solid #e2e8f0; border-radius: 12px; box-shadow: 0 4px 6px -1px rgba(0,0,0,0.05); }
  .bar-row { display: flex; align-items: center; margin-bottom: 1.5rem; }
  .bar-row:last-child { margin-bottom: 0; }
  .bar-label { width: 40%; font-weight: 600; color: #334155; font-size: 1.05em; }
  .bar-track { width: 60%; background: #e2e8f0; border-radius: 6px; height: 36px; position: relative; display: flex; align-items: center; }
  .bar-fill { height: 100%; border-radius: 6px; display: flex; align-items: center; justify-content: flex-end; padding-right: 15px; color: white; font-weight: 700; font-size: 0.95em; transition: width 1.5s ease-in-out; }
  .fill-blue { background: #3b82f6; }
  .fill-gray { background: #94a3b8; }
  .fill-red { background: #ef4444; }
  
  /* Code Blocks */
  pre { background: #0f172a; color: #f8fafc; padding: 2rem; border-radius: 12px; overflow-x: auto; font-size: 0.95em; box-shadow: inset 0 4px 6px rgba(0,0,0,0.5); margin: 2.5em 0; border: 1px solid #334155; }
  code { font-family: 'Fira Code', Consolas, Monaco, monospace; }
  img { max-width: 100%; border-radius: 12px; box-shadow: 0 10px 15px -3px rgba(0,0,0,0.1); margin: 3rem auto; display: block; }
</style>

<!-- Sidebar Navigation -->
<div class="sidebar">
  <h3>Contents</h3>
  <a href="#abstract">Abstract</a>
  <a href="#intro">Introduction & Context</a>
  <a href="#data">Data Architecture & EDA</a>
  <a href="#methodology">Methodology & Algorithms</a>
  <a href="#audit">The Leakage Audit</a>
  <a href="#results">Validation & Results</a>
  <a href="#limitations">Honest Limitations</a>
  <a href="#playbook">Ranked Action Playbook</a>
  <a href="#reproducibility">Reproducibility & Credits</a>
</div>

<!-- Main Document Content (Using strict HTML to prevent GitHub Markdown truncation) -->
<div class="content">

  <h1>Predicting Content Decay in Organic Search: A Baseline vs. ML Validation Framework</h1>
  
  <div class="meta-banner">
    <span class="meta-badge"><strong>Lead Developer:</strong> Humayun Naseem</span>
    <span class="meta-badge"><strong>Company:</strong> FlyRank AI</span>
    <span class="meta-badge"><strong>Role:</strong> Machine Learning Intern</span>
    <span class="meta-badge"><strong>Unit of Analysis:</strong> content_hash_id</span>
  </div>
  
  <h2 id="abstract">Abstract</h2>
  <div class="abstract-box">
    Does a supervised machine learning classifier outperform a hardcoded heuristic rule in predicting organic content decay for enterprise editorial triage? To empirically answer this, we analyzed a pseudonymized 30,000-page development sample extracted from an underlying 519,606-row enterprise search warehouse, evaluating trailing 90-day search visibility signals. We established a baseline heuristic model relying on content staleness and historical search demand, and subsequently compared its classification precision against a tuned Random Forest ensemble architecture. Initial predictive modeling yielded an anomalous, mathematically impossible 1.000 precision score; however, a rigorous architectural audit revealed severe temporal feature leakage driven by target-derived monthly comparison variables and forward-looking click windows. Upon strictly purging all temporally contaminated features and restructuring the validation protocol from a standard randomized split to a rigorous Grouped Client Split, the machine learning classifier's predictive precision fell to exactly 0.000. This research conclusively demonstrates that for complex, low-signal organic search datasets lacking deep longitudinal off-page features, the mathematically transparent baseline heuristic (achieving 0.360 precision) remains an operationally superior and substantially more robust triage mechanism than an unregularized supervised machine learning classifier.
  </div>
  
  <h2 id="intro">Introduction and Industry Problem Statement</h2>
  <p>Organic search traffic functions as a foundational, compounding digital asset for modern enterprises. Unlike paid user acquisition channels—which require continuous and often escalating capital allocation to sustain inbound traffic—well-optimized organic web content possesses the unique capacity to capture high-intent search traffic passively over extended temporal horizons. However, the digital publishing ecosystem is inherently non-stationary. High-performing web pages systematically undergo degradation, a pervasive phenomenon characterized in enterprise Search Engine Optimization (SEO) engineering as "content decay."</p>
  
  <p>Content decay manifests through subtle or abrupt losses in Search Engine Result Page (SERP) visibility, depressed keyword rankings, collapsing Click-Through Rates (CTR), and a general deterioration of user engagement metrics. The macro-environmental factors driving this decay are multifaceted and continuous. Competitors continuously publish fresher, more comprehensive digital resources; search engine ranking algorithms iteratively update their core semantic evaluation parameters; and structural alterations to SERP layouts—such as the aggressive proliferation of generative AI answer boxes (AI Overviews) and zero-click featured snippets—displace traditional organic listings further down the viewport.</p>
  
  <p>For enterprise search operations like FlyRank, which manage vast, multi-client portfolios comprising hundreds of thousands of individual URLs, identifying the precise onset of structural content decay represents a critical logistical bottleneck. Editorial teams operate under strict human resource and capital constraints; an editor can only execute a finite volume of page audits, content rewrites, and structural optimizations within a given publishing cycle. Consequently, deciding exactly which specific pages warrant immediate human intervention versus which assets should remain untouched is fundamentally an optimization problem of resource allocation.</p>
  
  <p>Traditional content maintenance workflows rely heavily on lagging indicators—such as reacting to a precipitous drop in monthly enterprise revenue or conducting sporadic, highly reactive manual traffic audits. These traditional methodologies inherently ensure that human intervention occurs only after substantial commercial value has already been forfeited. To solve this scalability challenge, automated triage systems have traditionally relied on rudimentary, hand-written heuristic rules. For instance, an enterprise might enforce a rigid business rule flagging any URL that has not been modified in over 180 days and maintains an impression volume exceeding a static threshold. While computationally instantaneous and entirely transparent, these hardcoded heuristics are fundamentally brittle. They fail to capture multi-variable, non-linear interactions, cannot dynamically adapt to shifting vertical dynamics, and frequently confuse normal seasonal traffic volatility with genuine, structural content decay.</p>
  
  <p>This applied research initiative shifts the operational paradigm from reactive manual audits and brittle heuristics to an automated, data-driven predictive triage system. By framing the identification of content decay as a supervised binary classification challenge, we aim to rigorously test whether advanced machine learning architectures can ingest multi-dimensional behavioral signals to isolate decaying content more effectively than traditional rule-based filters.</p>
  
  <h2 id="data">Data Architecture and Exploratory Analysis</h2>
  <p>The foundational data fueling this computational investigation is derived directly from the FlyRank Machine Learning Internship data warehouse. This represents an anonymized, production-grade dataset containing exactly 519,606 individual rows, structured and stored in high-efficiency Apache Parquet columnar formatting to allow for out-of-core processing.</p>
  
  <p>To maintain computational tractability during iterative model experimentation while preserving deep statistical significance, we isolated a strictly controlled development sample consisting of 30,000 rows and 44 distinct feature columns. The atomic unit of analysis throughout this entire machine learning pipeline is defined strictly as a single pseudonymized content item, uniquely identified via its <code>content_hash_id</code>. To ensure absolute adherence to enterprise privacy standards and public safety directives, all raw query strings, explicit client domain names, proprietary page titles, and identifiable URL strings were permanently hashed or stripped during the initial Extract, Transform, Load (ETL) ingestion phase.</p>
  
  <table>
    <tr>
      <th>Data Dimension / Metric</th>
      <th>Count / Observation Value</th>
      <th>Analytical Implication</th>
    </tr>
    <tr>
      <td><strong>Total Eligible Pages</strong></td>
      <td>30,000 pages × 44 columns</td>
      <td>Provides sufficient sample density for robust cross-validation splitting.</td>
    </tr>
    <tr>
      <td><strong>Pages with Downward Trend</strong></td>
      <td>16,262 (54.2% of sample)</td>
      <td>Establishes a highly balanced binary class distribution for classification.</td>
    </tr>
    <tr>
      <td><strong>Stale Pages (180+ days old)</strong></td>
      <td>9,929 URLs</td>
      <td>Filtered specifically for high search demand (minimum 500+ impressions).</td>
    </tr>
    <tr>
      <td><strong>Data Grain Integrity Check</strong></td>
      <td>Validated (Mathematically Unique)</td>
      <td>Confirms <code>content_hash_id</code> contains zero duplicate primary key violations.</td>
    </tr>
  </table>
  
  <h3>Exploratory Data Analysis (EDA) of Search Signals</h3>
  <p>Prior to passing any numerical feature matrices into a machine learning algorithm, an exhaustive Exploratory Data Analysis (EDA) was executed to validate the core economic and behavioral assumptions regarding content maturation and organic search visibility within the FlyRank ecosystem.</p>
  
  <ul>
    <li><strong>Signal 1: Staleness vs. Click-Through Rate (CTR).</strong> We partitioned the historical dataset into quartile age buckets to formally evaluate engagement degradation over time. The statistical analysis confirmed that older content universally suffers from structural engagement fatigue. Content situated within the newest quartile (Q1) exhibited a robust average CTR of 0.376. Conversely, content residing in the oldest quartile (Q4) experienced a severe depression, dropping to an average CTR of 0.299. <em>Verdict: Confirmed. Temporal staleness serves as a mathematically valid and highly predictive baseline flag trigger.</em></li>
    <li><strong>Signal 2: Search Volume Demand vs. Actual Clicks.</strong> Organic search traffic follows an extreme Pareto (power-law) distribution where a minute fraction of URLs capture the overwhelming majority of user interaction. Grouping the dataset into impression demand tiers proved this structural reality unequivocally: low-demand buckets generated a negligible average of 0.135 clicks, whereas high-demand tiers scaled exponentially to generate an average of 59.20 clicks per asset. <em>Verdict: Confirmed. Integrating search volume demand as a mandatory preliminary filter is essential to prevent human editorial bandwidth from being squandered on low-visibility, low-commercial-impact web pages.</em></li>
  </ul>
  
  <h3>The Data Contract and Feature Availability</h3>
  <p>To enforce absolute operational validity for production deployment, we established a rigorous Data Contract. Five core feature variables were mathematically audited and verified as strictly "knowable at the decision moment." This ensures they are available historically without introducing future look-ahead bias into the algorithm. These features are: <code>content_age_days</code>, <code>impressions_90d</code>, <code>clicks_90d</code>, <code>ctr_90d</code>, and <code>avg_position</code>.</p>
  
  <h2 id="methodology">Methodology and Algorithmic Formulation</h2>
  
  <h3>Defining the Target Variable</h3>
  <p>Translating the abstract, highly qualitative concept of enterprise "content decay" into a mathematically rigorous machine learning target required formulating a precise binary classification label. We engineered the target classification label, <code>is_declining_label</code>, derived directly from the underlying historical trajectory condition <code>trend_direction == "down"</code>. This proxy label effectively captures observed trailing performance trends, isolating pages that are actively losing market share.</p>
  
  <h3>The Baseline Heuristic Model</h3>
  <p>To establish an absolute performance floor against which all advanced machine learning classifiers could be empirically measured, we encoded a transparent, hardcoded baseline heuristic rule. This baseline specifically targets mature, high-visibility web assets that are actively exhibiting symptoms of user disengagement and CTR fatigue:</p>
  
<pre><code># The Operational Baseline Triage Heuristic
if content_age_days > 180 and impressions_90d > 500:
    reason_code = "STALE_HIGH_DEMAND"
    action_label = "PRIORITY_REFRESH"
    return True
else:
    return False
</code></pre>

  <p>When evaluated strictly across the held-out test partitions, this baseline rule achieved a foundational Baseline Precision of 0.360 and a Baseline Recall of 0.201, establishing a concrete and highly transparent benchmark for operational utility within the editorial team.</p>

  <h3>Machine Learning Architecture: The Random Forest</h3>
  <p>To determine if non-linear feature interactions and high-dimensional behavioral signals could elevate predictive performance beyond this simple rule-based heuristic, we deployed a supervised Random Forest classification architecture. The Random Forest is a highly robust ensemble learning method predicated upon the statistical mechanics of Bootstrap Aggregating (Bagging).</p>
  
  <p>The algorithm constructs a massive forest of independent decision trees during the training phase by sampling the original training dataset with replacement. Furthermore, to deliberately decorrelate the individual trees and drastically mitigate variance (overfitting), the algorithm randomly subsets the available feature space ($m = \sqrt{p}$) at every single node split.</p>
  
  <p>The core mathematical objective function governing each discrete node split within the constituent decision trees is explicitly designed to maximize information gain by aggressively minimizing the Gini Impurity, which is formally defined as:</p>
  
  $$ G = 1 - \sum_{k=1}^{C} p_k^2 $$
  
  <p>where $p_k$ represents the empirical probability that a given web content asset is classified into class $k$ (e.g., declining vs. stable). By executing this minimization recursively, the tree isolates the purest possible classifications. The final ensemble prediction is rendered via a deterministic majority voting mechanism aggregated across all generated trees in the forest.</p>

  <h2 id="audit">The Feature Leakage Audit</h2>
  <p>The execution of our machine learning pipeline encountered a profound and highly instructive validation crisis. Initial training of the Random Forest model—utilizing a standard, randomized 80/20 train-test split—yielded an impossible, mathematically flawless performance metric: <strong>1.000 Precision and 1.000 Recall</strong>. Recognizing immediately that a 100% accurate machine learning model on highly volatile, complex real-world web data is an absolute statistical impossibility, a rigorous architectural audit was immediately executed.</p>
  
  <p>This forensic audit successfully unmasked two catastrophic forms of feature leakage that completely invalidated the initial model:</p>
  
  <ol>
    <li><strong>The Temporal Trap (<code>future_clicks_30d</code>):</strong> During the initial feature ingestion phase, a forward-looking metric tracking user clicks in the <em>subsequent</em> 30 days was inadvertently concatenated into the independent feature set. Because this variable literally encoded future user behavior directly into the input training matrix, the decision trees achieved near-perfect predictive separation by simply looking straight into the future.</li>
    <li><strong>Target-Derived Proxies (<code>trend_pct</code>):</strong> The feature engineering pipeline had erroneously passed variables encoding the exact month-over-month mathematical comparisons that were utilized to explicitly construct the target <code>trend_direction</code> label in the first place. Consequently, the algorithm was not learning behavioral decay patterns; it was merely reverse-engineering its own deterministic label formula.</li>
  </ol>
  
  <p>To resolve this catastrophic data integrity violation, both leakage vectors were permanently purged from the environment. However, an additional architectural vulnerability remained regarding cross-validation.</p>
  
  <h3>Validation Protocol: The Grouped Client Split</h3>
  <p>Recognizing that standard random splitting allows pages from the exact same client domain to leak across both the training and testing folds, the model was still capable of "cheating" by memorizing specific, domain-level traffic baselines (e.g., memorizing that Client A always has higher traffic than Client B). To neutralize this, we engineered a strict <strong>Grouped Client Split</strong> (utilizing <code>GroupShuffleSplit</code> mapped on the <code>client_id</code> feature).</p>
  
  <p>This advanced validation protocol ensured that all pages belonging to a specific client were placed exclusively in either the training set or the test set—never both. This forced the machine learning model to evaluate its predictive performance entirely on unseen client domains, thereby testing true, generalized algorithmic learning.</p>
  
  <h2 id="results">Validation and Results</h2>
  <p>Following the complete removal of all target-derived proxies and the enforcement of the rigorous Grouped Client Split validation protocol, the Random Forest classifier was completely stripped of its ability to cheat. It was forced to learn and predict exclusively from genuine, historical trailing behavioral momentum.</p>

  <table>
    <tr>
      <th>Feature Name</th>
      <th>Importance Weight</th>
      <th>Analytical Interpretation (Pre-Audit Leaky Context)</th>
    </tr>
    <tr>
      <td><code>search_volume</code></td>
      <td>0.444037</td>
      <td>Dominant split driver; highly correlated with absolute traffic scale.</td>
    </tr>
    <tr>
      <td><code>content_age_days</code></td>
      <td>0.266486</td>
      <td>Secondary structural driver indicating temporal content maturation.</td>
    </tr>
    <tr>
      <td><code>avg_position</code></td>
      <td>0.262398</td>
      <td>Tertiary positional driver dictating SERP placement and visibility.</td>
    </tr>
    <tr>
      <td><code>impressions_90d</code></td>
      <td>0.020686</td>
      <td>Suppressed statistical weight due to severe leakage confounding.</td>
    </tr>
    <tr>
      <td><code>ctr_90d</code></td>
      <td>0.006393</td>
      <td>Negligible algorithmic contribution in the pre-audit feature space.</td>
    </tr>
  </table>
  
  <p>When evaluated upon the strictly controlled, mathematically honest validation split—where all look-ahead variables were purged and domain-level memorization was successfully blocked by the client group architecture—the machine learning model's predictive capability entirely collapsed.</p>

  <div class="bar-chart-container">
    <div class="bar-row">
      <div class="bar-label">Baseline Heuristic</div>
      <div class="bar-track"><div class="bar-fill fill-blue" style="width: 36%;">0.360</div></div>
    </div>
    <div class="bar-row">
      <div class="bar-label">Leaky ML Model (Cheating)</div>
      <div class="bar-track"><div class="bar-fill fill-red" style="width: 100%;">1.000</div></div>
    </div>
    <div class="bar-row">
      <div class="bar-label">Honest ML Model (No Leakage)</div>
      <div class="bar-track"><div class="bar-fill fill-gray" style="width: 5%;">0.000</div></div>
    </div>
  </div>

  <p><strong>Empirical Conclusion:</strong> The initial Week 5 machine learning model was methodologically flawed due to severe feature leakage. Once all variables utilized to construct the target label were rigorously purged from the matrix, the supervised classifier's precision dropped to exactly 0.000. Consequently, the highly transparent, hardcoded baseline heuristic (achieving 0.360 precision) definitively outperforms the non-leaky Random Forest classifier on this specific, restricted feature space.</p>

  <h2 id="limitations">Limitations and Honest Framing</h2>
  <p>This applied research study highlights a vital, highly sobering reality often obscured in enterprise machine learning literature: deploying complex, highly parameterized modeling architectures does not inherently compensate for foundational data limitations. Once our 30,000-row development sample was strictly sanitized of all temporally leaky variables and subjected to rigorous grouped cross-validation, the remaining feature set simply lacked sufficient predictive signal density for an ensemble classifier to reliably separate structurally declining URLs from stable assets.</p>
  
  <p>Furthermore, the data architecture relies exclusively on trailing metrics sourced entirely from Google Search Console (GSC). While GSC provides unmatched, deterministic visibility into internal search performance, it represents an inherently closed system. It is structurally incapable of capturing the exogenous, off-page variables that heavily dictate content decay in real-world production environments—such as aggressive competitor backlink acquisitions, sudden macroeconomic shifts in user search intent, or structural alterations in SERP composition driven by automated generative AI summaries.</p>
  
  <h2 id="playbook">Ranked Action Playbook</h2>
  <p>Because empirical validation definitively proved that the mathematically honest machine learning classifier fails to outperform the transparent rule-based approach, the final operational playbook explicitly prioritizes the baseline heuristic. This maximizes human editorial efficiency while eliminating unpredictable algorithmic noise.</p>
  
  <ul>
    <li><strong>Step 1: Deploy the Baseline Triage Queue.</strong> The editorial team must export and operationalize the <code>baseline_action_score.csv</code> dataset, extracting only the top-priority editorial candidates tagged explicitly with the <code>STALE_HIGH_DEMAND</code> reason code.</li>
    <li><strong>Step 2: Enforce Impression Tier Filtering.</strong> Exploratory data analysis confirmed that high impression tiers drive the vast majority of meaningful user clicks. Editorial teams must force-rank the operational triage queue in strict descending order based on trailing 90-day impression volume (<code>impressions_90d</code>).</li>
    <li><strong>Step 3: Mandatory Human Editorial Verification.</strong> Human editors must manually inspect the live Search Engine Results Pages (SERPs) for the Top 20 flagged candidates prior to initiating any content rewrites or structural updates. This manual verification ensures human editors diagnose the actual root cause of CTR depression (e.g., confirming whether an AI Overview snippet has permanently displaced the organic ranking).</li>
    <li><strong>Step 4: Strict Automation Ban.</strong> Under no circumstances should any predictive scoring model, heuristic filter, or automated script be directly integrated via API into an enterprise Content Management System (CMS) to autonomously overwrite, redirect, or delete web pages without mandatory human sign-off. The cost of a False Positive (deleting a healthy page) is simply too high.</li>
  </ul>
  
  <h2 id="reproducibility">Reproducibility and Data Credits</h2>
  <p>In strict accordance with rigorous open-science and enterprise engineering standards, all underlying Python codebase architectures, data extraction pipelines, feature leakage audit scripts, and baseline generation Jupyter notebooks are fully documented and publicly archived for peer review and replication.</p>
  
  <ul>
    <li><strong>Primary Code Repository:</strong> <a href="https://github.com/humcoder40/Flyrank_startup_notebook">github.com/humcoder40/Flyrank_startup_notebook</a></li>
  </ul>
  
  <h3 id="acknowledgments">Acknowledgments</h3>
  <p>This applied research initiative and machine learning engineering capstone was developed utilizing the enterprise production data warehouse provided exclusively by the FlyRank ML Internship program. We gratefully acknowledge FlyRank AI for supplying the underlying pseudonymized search datasets. For further technical documentation regarding their enterprise data architecture and applied SEO intelligence platforms, please visit <a href="https://flyrank.ai">https://flyrank.ai</a>.</p>

</div>
