# Social Media Analytics & Fact-Checking Toolkit

This repository serves as a unified dual-utility workspace containing two standalone components developed for social media research and data validation. The scripts operate independently to handle separate dimensions of misinformation analysis.

## 🚀 Repository Structure

* **Code Part 1 (`cascade_viral_networks.ipynb`)**: A backend network science framework analyzing graph structures, information velocity, cascade trees, and bot clique propagation.
* **Code Part 2 (`fact_check_validator.ipynb`)**: A frontend interactive Google Colab application leveraging the Google Fact Check Tools API to audit user-submitted claims against verified global databases.

---

## 📊 Code Part 1: Viral Content & Network Centrality Analysis

This standalone notebook automates an end-to-end network modeling pipeline. It ingests historical sharing logs to identify coordinated bot amplifiers and calculate the physical propagation speed of viral rumors.

### Key Features
* **Account Typology Profiling**: Maps specific actor classifications (`Bot`, `Normal`, `InFluencer`, `Lurker`) and sharing habits directly from dataset logs.
* **Patient Zero Identification**: Automatically reconstructs misinformation transmission pathways to pinpoint the precise source root node (`Tweet_ID` $\rightarrow$ `User_ID`) that initiated a cascade.
* **Information Velocity Analysis**: Measures and contrasts the acceleration rate of organic sharing against artificial amplification spikes driven by automated networks.
* **Coordinated Bot Clique Detection**: Implements `nx.find_cliques` to isolate dense subgraphs of malicious accounts operating in perfect synchronization during initial target broadcasts (Step 0).

### Output Dashboard
The module compiles its mathematical outputs into a high-resolution 3-panel visual asset (`misinformation_analysis_dashboard.png`) displaying the structural cascade hierarchy, information curves, and the isolated hub orchestrator node.

![Misinformation Analysis Dashboard](misinformation_analysis_dashboard.png)

### Requirements & Libraries
```bash
pip install kagglehub pandas networkx matplotlib
```

---

## ⚙️ Code Part 2: Interactive Google Fact-Check Validator

This independent module implements a lightweight, real-time claim authentication web application inside a live Google Colab workbook. It relies directly on the **Google Fact Check Tools API** to discover published journalistic audits.

### Key Features
* **Live API Search Layer**: Dispatches network requests to `claims:search` endpoints via specialized parameters to parse global debunking records.
* **Dynamic `ipywidgets` UI**: Renders custom text entry bars and event-driven submission buttons directly within the cell output area.
* **Conditional Verdict Badging**: Evaluates metadata text dynamically to append colored priority markers based on truth severity metrics (e.g., **Red Badges for False/Misleading statements**, **Green for Verified Accuracy**, and **Yellow for Mixed Results**).
* **Direct Source Citation**: Generates hyperlinked index cards that contain the original speaker, date, publisher attribution, and direct routing back to the publisher’s full review page.

### Live Application Output Interface
The application renders an interactive widget interface allowing real-time claim validation:

![Google Fact Check Tools API Quick Checker UI](fact_check_output.png)

*Example execution workflow depicted above:* Querying the classic myth *"human uses 10% of the brain"* instantly fetches data payloads from verified publishers, returning a visual **[FALSE]** badge along with explicit source tracking parameters.

### Requirements & Libraries
```bash
pip install requests ipywidgets ipython
```

---

## 🛠️ Global Execution Quick-Start
1. Upload both `.ipynb` files to your personal Google Drive or directly hook this repository up to your Google Colab instance.
2. Ensure you have your personal Kaggle validation token installed for **Code Part 1** to permit automated dataset downloads.
3. Verify that your Google Cloud Platform API configuration permits external requests to the Google Fact Check Tools API for **Code Part 2**.
