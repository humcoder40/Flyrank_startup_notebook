<style>
  body {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif;
    line-height: 1.7;
    color: #24292e;
    max-width: 900px;
    margin: 0 auto;
    padding: 2rem;
  }
  h1 {
    font-size: 2.5em;
    font-weight: 800;
    text-align: center;
    color: #111827;
    margin-bottom: 0.5em;
  }
  h3 {
    font-size: 1.5em;
    color: #1f2937;
    border-bottom: 2px solid #e5e7eb;
    padding-bottom: 0.3em;
    margin-top: 2em;
  }
  .metadata-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1.5rem;
    background: #f9fafb;
    padding: 1.5rem;
    border-radius: 8px;
    border: 1px solid #e5e7eb;
    margin-bottom: 2rem;
  }
  .metadata-item strong {
    color: #4b5563;
    font-size: 0.85em;
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }
  .abstract-box {
    background-color: #f0fdf4;
    border-left: 4px solid #22c55e;
    padding: 1.5rem;
    margin: 2rem 0;
    border-radius: 0 8px 8px 0;
    font-style: italic;
  }
  table {
    width: 100%;
    border-collapse: collapse;
    margin: 2rem 0;
    box-shadow: 0 1px 3px rgba(0,0,0,0.1);
  }
  th {
    background-color: #f3f4f6;
    text-align: left;
    padding: 12px;
    font-weight: 600;
  }
  td {
    padding: 12px;
    border-bottom: 1px solid #e5e7eb;
  }
  img {
    max-width: 100%;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0,0,0,0.1);
    margin: 2rem 0;
  }
</style>
# Predicting Content Decay in Organic Search: A Baseline ML Approach on Real Production Data

<div class="metadata-grid">
  <div class="metadata-item">
    <strong>Author</strong><br>
    Humayun Naseem
  </div>
  <div class="metadata-item">
    <strong>Role</strong><br>
    ML Engineering Intern, FlyRank AI
  </div>
  <div class="metadata-item">
    <strong>Institution</strong><br>
    Information Technology University
  </div>
  <div class="metadata-item">
    <strong>Date</strong><br>
    August 2026
  </div>
  <div class="metadata-item">
    <strong>Dataset</strong><br>
    FlyRank ML Internship Dataset (79M row warehouse)
  </div>
  <div class="metadata-item">
    <strong>Code Repository</strong><br>
    <a href="https://github.com/humcoder40/Flyrank_startup_notebook">github.com/humcoder40/Flyrank_startup_notebook</a>
  </div>
</div>

<div class="abstract-box">
  <strong>ABSTRACT:</strong> Web content decay represents a critical compounding loss in search engine optimization, typically managed through reactive, manual audits. This research investigates the efficacy of machine learning in proactively predicting content requiring editorial intervention by analyzing trailing 90-day search performance signals. Utilizing a production-scale warehouse of 79 million anonymized search records, we developed a Random Forest classifier and evaluated it against a rigid heuristic baseline. To ensure absolute mathematical honesty and prevent temporal leakage, validation was conducted via a strict Grouped Client Split. The resulting artifact is a prioritized, directional action playbook engineered to optimize human editorial bandwidth without risking automated, algorithmic overwrites.
</div>

### 1. Introduction and Problem Statement
The lifecycle of digital content is inherently subject to degradation. Over time, high-performing web assets inevitably experience decay in search visibility, keyword rankings, and user engagement. For enterprise editorial teams, identifying the onset of this decay is a persistent logistical challenge. Relying on lagging indicators or manual traffic audits dictates that intervention only occurs after significant commercial value has already been lost.

The primary objective of this architecture is to transition content maintenance from a reactive audit process to a predictive, data-driven triage system. By analyzing historical behavioral signals rather than semantic content, we construct a decision-support mechanism that flags assets exhibiting early-stage decay symptoms.
