# 🔍 Code Part 2: Google Fact Check Tools API — Interactive Claim Validator

## Overview

This notebook is a **frontend interactive claim-checking application** built for Google Colab. It queries the **Google Fact Check Tools API** to audit user-submitted claims against verified fact-check databases from publishers worldwide (Snopes, PolitiFact, AFP Fact Check, Reuters Fact Check, and many more).

It is the second standalone component of the [Social Media Analytics & Fact-Checking Toolkit](../README.md), operating independently from the viral network analysis in Code Part 1.

---

## ✨ Features

- **Interactive widget UI** — text input, language selector, and a one-click "Check Claim" button
- **Color-coded verdict badges** — green (True), red (False/Misleading), amber (Mixed), grey (Unrated)
- **Multi-language support** — query in English, German, French, Spanish, Portuguese, or Arabic
- **Secure API key handling** — key is entered via hidden `getpass` prompt, never stored in cells
- **Clickable source links** — each result links directly to the original fact-check article

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

**In Google Colab:**
1. Upload `fact_check_validator.ipynb` or open it from the repository
2. Run Cell 1 (imports)
3. Run Cell 2 → paste your API key when prompted (hidden input)
4. Run Cell 3 → the interactive widget appears below the cell

**In Jupyter Notebook (local):**
```bash
pip install ipywidgets requests
jupyter notebook fact_check_validator.ipynb
```

---

## 🗂️ File Structure

```
fact_check_validator.ipynb   ← This notebook (Code Part 2)
README_FactChecker.md        ← This file
```

---

## 🔧 How It Works

```
User types a claim
        ↓
Widget sends query to Google Fact Check Tools API
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
| `requests` | HTTP calls to the Google API |
| `ipywidgets` | Interactive UI widgets (text box, dropdown, button) |
| `IPython.display` | Rendering HTML output in the notebook |
| `getpass` | Secure (hidden) API key input |

All packages are available by default in Google Colab. For local Jupyter, install with:

```bash
pip install requests ipywidgets
```

---

## ⚠️ Security Notes

- **Never hardcode your API key** in a notebook cell — it will be committed to version control and publicly exposed.
- Always use `getpass.getpass()` or environment variables to pass secrets at runtime.
- If you accidentally commit a key, revoke it immediately in [Google Cloud Console](https://console.cloud.google.com/apis/credentials) and generate a new one.

---

## 🔗 Related Components

| Component | Description |
|---|---|
| [Code Part 1 — Viral Network Analysis](../cascade_viral_networks.ipynb) | Backend network science framework analyzing graph structures, information velocity, cascade trees, and bot clique propagation |
| [Code Part 2 — Fact Check Validator](./fact_check_validator.ipynb) | **This notebook** — frontend interactive claim checker using Google Fact Check Tools API |

---

## 👥 Authors

- **Mherub Ahsan** ([@meharab004](https://github.com/meharab004)) — Fact Check Validator (Code Part 2)
- **Nishitha Velagala** ([@NishithaVelagala](https://github.com/NishithaVelagala)) — Viral Network Analysis (Code Part 1)

---

## 📄 License

This project is for academic/research purposes. See the root [LICENSE](../LICENSE) file for details.
