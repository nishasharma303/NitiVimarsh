# NitiVimarsh AI  
### Policy Consequence Intelligence Engine for Bharat

---

## 📌 Overview

**NitiVimarsh AI** is an interactive policy consequence simulator designed to analyze the ripple effects of Indian government policies across multiple stakeholder groups.

Unlike static policy explainers or eligibility checkers, NitiVimarsh simulates *how a policy propagates through the economy*, quantifies its impact, and presents explainable, scenario-based outcomes.

The system models policies as structured variables, builds stakeholder causal graphs, and computes second-order effects using scenario-driven simulation.

---

## 🎯 Problem Statement

Government policies are often complex and difficult to interpret for:

- Citizens
- MSMEs
- Farmers
- Policymakers

Existing tools typically:
- Summarize policy text
- Provide eligibility checks
- Offer static tax calculators

They do **not** simulate ripple effects or quantify stakeholder impact under varying assumptions.

NitiVimarsh addresses this gap by transforming policy evaluation into an interactive consequence intelligence engine.

---

## 🚀 Core Features

### 🔍 Policy Extraction
- Parses policy text
- Extracts structured variables (type, target, parameters, timeline)

### 📊 Baseline Data Retrieval
- Retrieves economic indicators (GDP, inflation, employment)
- Validates recency and completeness
- Stores source metadata for transparency

### 🔗 Causal Graph Modeling
- Directed stakeholder graph
- Weighted influence edges
- Ripple propagation logic

### ⚙ Scenario-Based Simulation
- Elasticity modeling
- Adoption rate
- Compliance rate
- Pass-through rate
- Monte Carlo simulation for uncertainty modeling

### 📈 Shock Index
- Quantified impact score per stakeholder
- Positive / Negative / Neutral classification
- Confidence metrics

### 📉 Trade-off Visualization
- Stakeholder comparison
- Before vs After analysis
- Sensitivity heatmaps

### 📄 Explainable Reports
- Step-by-step impact breakdown
- Uncertainty indicators
- Multi-format output (JSON / HTML / PDF)

---

## 🏗 System Architecture

The system follows a modular pipeline architecture:

1. **Policy Extractor**
2. **Baseline Retriever**
3. **Causal Graph Builder**
4. **Simulation Engine**
5. **Report Generator**

Impact propagation is modeled using a directed acyclic graph (DAG) and scenario-based Monte Carlo simulation.

See `design.md` for detailed architecture and data models.

---


