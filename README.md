# 🪟 TradeNex — AI-Powered Tile Material Estimator
**F26-10 | AI-2002 Artificial Intelligence | FAST NUCES Lahore**  
**Instructor:** Dr. Hajra Waheed

---
## 📌 Project Overview

TradeNex is an end-to-end AI system that estimates tile installation materials and recommends grout colours in real time. It was built for the TradeNex platform to replace manual estimation with machine-learning-driven predictions.

Given an installation area, tile dimensions, thickness, location type, and tile colour, the system predicts:
- Clips and wedges required (with box count)
- Grout volume (mL) and number of grout tubes
- Minimum recommended grout width
- Three grout colour recommendations — Seamless, Balanced, Contrast

---

## 📁 Repository Structure

```
├── F26-10_phase1.pdf         # Proposal
├── F26-10_Phase2.ipynb       # Data generation, preprocessing, EDA
├── F26-10_Phase3.ipynb       # Model training, evaluation, metrics
├── F26-10_Phase4.ipynb       # Model evaluation, hyperparameter tuning         
├── F26-10_Phase5.ipynb       # Final Streamlit web application
├── F26-10_Phase6.ipynb       # Final Streamlit web application (Gradio-based notebook version)
├── F26-10_Final_Report       # Final Report
├── README.md                 # This file
```

---

## ⚙️ Setup & Installation

### Requirements
- Python 3.8 or higher
- pip

### Install dependencies

```bash
pip install streamlit scikit-learn pandas numpy matplotlib seaborn gradio plotly
```

---

## 🚀 How to Run

### Option 1 — Streamlit Web App (recommended)

```bash
streamlit run F26-10_Phase5.py
```

The app opens automatically at `http://localhost:8501`

### Option 2 — Gradio Notebook (Google Colab)

Open `F26-10_Phase5.ipynb` in Google Colab and run all cells.  
A public shareable link is generated automatically via `demo.launch(share=True)`.

### Option 3 — Run Phase notebooks sequentially

```
Phase 2 → Phase 3 → Phase 4
```

Each notebook is self-contained and regenerates the dataset from scratch using `random.seed(42)`.

---

## 🧠 AI Models

| Model | Algorithm | Task | Performance |
|---|---|---|---|
| Material Estimator | RandomForestRegressor | Predict clips, grout volume, tubes | R² = 0.70 – 0.77 |
| Balanced Colour | RandomForestClassifier | Predict balanced grout colour | Accuracy = 52.5% |
| Contrast Colour | RandomForestClassifier | Predict contrast grout colour | Accuracy = 30.0% |

- **Training data:** 200 synthetic tile installation scenarios  
- **Train/test split:** 80% / 20% (random_state=42)  
- **Hyperparameters:** n_estimators=200, max_depth=10, min_samples_leaf=2, class_weight=balanced

---

## 📊 Dataset

The dataset is fully synthetic — generated using real domain formulas from structured interviews with the client CEO and an architect. No public dataset exists for tile-specific installation estimation.

**Features (13):** installation area, tile length, tile width, tile thickness, location type (one-hot), tile tone (one-hot), tile lightness (one-hot)

**Targets (5):** clips, grout volume (mL), grout tubes, balanced colour label, contrast colour label

---

## 🖥️ Web Application — Features

| Tab | Content |
|---|---|
| Results | Real-time material estimates + colour recommendation cards + grout width range visual |
| Analytics | Feature importance chart, model metrics table, area vs clips scatter plot |
| How to Use | Step-by-step guide, output explanations, architecture diagram |

---

## 👥 Team

**Group:** F26-10  
**Course:** AI-2002 Artificial Intelligence  
**University:** National University of Computer and Emerging Sciences — Lahore  
**Instructor:** Dr. Hajra Waheed | **TA:** Talha Azhar  
**Members:** Sehrish Ejaz, Mahrukh Zubair, Ayesha Arshad
