# 🔍 Code Part 2: Google Fact Check Tools API — Interactive Claim Validator

## Overview

This notebook is a **frontend interactive claim-checking application** built for Google Colab. It queries the **Google Fact Check Tools API** to audit user-submitted claims against verified fact-check databases from publishers worldwide (Snopes, PolitiFact, AFP Fact Check, Reuters Fact Check, and many more).

It is the second standalone component of the [Social Media Analytics & Fact-Checking Toolkit](../README.md), operating independently from the viral network analysis in Code Part 1.

---

## ✨ Features

- **Interactive widget UI** — text input and a one-click "Check Claim" button
- **Color-coded verdict badges** — green (True), red (False/Misleading), amber (Mixed), grey (Unrated)
- **Clickable source links** — each result links directly to the original fact-check article
- **Secure API key handling** — key is entered via hidden `getpass` prompt at the top of the cell, never stored in the notebook

---

## 🚀 Getting Started

### 1. Prerequisites

| Requirement | Details |
|---|---|
| Python | 3.8+ |
| Environment | Google Colab (recommended) or Jupyter Notebook |
| API Key | Google Fact Check Tools API key (free) |

### 2. Enable the Google Fact Check Tools API

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a project (or select an existing one)
3. Navigate to **APIs & Services → Library**
4. Search for **"Fact Check Tools API"** and click **Enable**
5. Go to **APIs & Services → Credentials → Create Credentials → API Key**
6. Copy your API key

> 💡 **Tip:** Restrict the key to the Fact Check Tools API only to limit exposure if it is ever leaked.

### 3. Run the Notebook

**In Google Colab (recommended):**
1. Open `Factcheck.ipynb` from the repository in Google Colab
2. Run the single cell — it will immediately prompt: `Enter your Google Fact Check Tools API Key:`
3. Paste your API key (input is hidden) and press Enter
4. The interactive widget UI appears below — type a claim and click **Check Claim**

**In Jupyter Notebook (local):**
```bash
git clone https://github.com/NishithaVelagala/Digital_Objects_Misinformation_Spread
cd Digital_Objects_Misinformation_Spread
pip install requests ipywidgets
jupyter notebook Factcheck.ipynb
```
Then run the single cell, enter your API key when prompted, and use the widget.

---

## 🗂️ File Structure

```
Factcheck.ipynb          ← This notebook (Code Part 2) — single cell
README_FactChecker.md    ← This file
```

---

## 🔧 How It Works

```
Run the cell → prompted for API key (hidden input)
        ↓
Type a claim into the widget text box
        ↓
Click "Check Claim"
        ↓
Widget queries Google Fact Check Tools API
        ↓
API searches global fact-check databases
        ↓
Results rendered as HTML verdict cards
  ├── 🟢 TRUE / CORRECT / ACCURATE
  ├── 🔴 FALSE / FAKE / MISLEADING
  ├── 🟡 PARTIALLY TRUE / MIXTURE
  └── ⚪ No rating available
```

Each result card shows:
- The original claim text and who stated it
- The fact-checking publisher (e.g., Reuters, AFP, Snopes)
- A color-coded verdict badge
- A direct link to the full fact-check article

---

## 📦 Dependencies

| Package | Purpose |
|---|---|
| `requests` | HTTP calls to the Google Fact Check Tools API |
| `ipywidgets` | Interactive UI widgets (text input, button) |
| `IPython.display` | Rendering HTML verdict cards in the notebook |
| `getpass` | Secure hidden API key input at runtime |

All packages are available by default in Google Colab. For local Jupyter, install with:

```bash
pip install requests ipywidgets
```

---

## ⚠️ Security Notes

- **Never hardcode your API key** in a notebook cell — it will be committed to version control and publicly exposed.
- Always use `getpass.getpass()` to pass your key at runtime — it stays in memory only for that session.
- If you accidentally commit a key, revoke it immediately in [Google Cloud Console](https://console.cloud.google.com/apis/credentials) and generate a new one.

---

## 🔗 Related Components

| Component | Description |
|---|---|
| [Code Part 1 — Viral Network Analysis](../cascade_viral_networks.ipynb) | Backend network science framework analyzing graph structures, information velocity, cascade trees, and bot clique propagation |
| [Code Part 2 — Fact Check Validator](./Factcheck.ipynb) | **This notebook** — frontend interactive claim checker using Google Fact Check Tools API |

---

## 👥 Authors

- **Mherub Ahsan** ([@meharab004](https://github.com/meharab004)) — Fact Check Validator (Code Part 2)
- **Nishitha Velagala** ([@NishithaVelagala](https://github.com/NishithaVelagala)) — Viral Network Analysis (Code Part 1)

---

## 📄 License

This project is for academic/research purposes. See the root [LICENSE](../LICENSE) file for details.
