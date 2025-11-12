# TAWKEED-CP: Bilingual Smishing Detection with Conformal-Prediction Guarantees
# Project of Mohammed Rasol Salim Al Saidat
#October 2025

**TAWKEED-CP** is a bilingual (Arabic–English) smishing detection framework that combines:
- **Morphology-aware text processing** (Arabic diacritics/alif-ya canonicalization, clitic segmentation; English lemmatization)  
- **Unicode-aware risk signals** (URLs, digits across scripts, **zero-width**, **confusables**)  
- A strong sparse text **baseline** (TF-IDF word/char + Logistic Regression) with **per-language temperature calibration**  
- **Split/Mondrian Conformal Prediction (CP)** for *distribution-free* finite-sample **coverage guarantees** per cell *(language × risk band)*

The framework returns **set-valued predictions** (singleton → automate, empty → abstain) with user-selected miscoverage \(\alpha\), so you can **tune reliability vs. automation** while keeping guarantees.

---

## ✨ Highlights
- **Bilingual reliability:** Valid coverage for **Arabic** and **English** across risk bands  
- **Operational efficiency:** At \(\alpha=0.05\), automation typically exceeds **95%** with abstention \< **5%**  
- **Robustness:** Unicode/spacing/homoglyph attacks tested with modest coverage degradation  
- **Reproducibility:** Colab runbook + pinned environment + CI

---

## 🚀 Quick start

### 1) Clone & environment

```bash
git clone https://github.com/<your-org>/tawkeed-cp.git
cd tawkeed-cp

# Option A: pip
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt

# Option B: conda
conda env create -f environment.yml
conda activate tawkeed-cp
