# Network Intrusion Detection System (NIDS) — UNSW-NB15

A supervised machine learning classification pipeline built in Python to evaluate tree-based ensemble models (**Random Forest** vs. **XGBoost**) for multi-vector network intrusion detection on the **UNSW-NB15** dataset.

## Objectives
- Address class imbalance and high-dimensional network flow features in modern intrusion detection.
- Compare detection performance, false-positive rates, and inference efficiency between **Random Forest** and **XGBoost**.
- Map top predictive network flow features (`sttl`, `ct_state_ttl`, `sbytes`, `dbytes`, `sload`) to practical SOC triage rules.

## Dataset & Preprocessing
- **Dataset:** UNSW-NB15 (9 attack categories: Fuzzers, Analysis, Backdoors, DoS, Exploits, Generic, Reconnaissance, Shellcode, Worms + Normal traffic).
- **Pipeline:**
  1. Dropped identifier leakage columns (`id`, `attack_cat` for binary classification) and handled categorical protocol fields (`proto`, `service`, `state`).
  2. Applied stratified train/test splitting to preserve minority attack distributions.
  3. Evaluated models using **Precision, Recall, Macro/Weighted F1-Score, and ROC-AUC** alongside confusion matrices and precision-recall curves.

## Results Summary
| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Random Forest** | `[XX.X%]` | `[0.XX]` | `[0.XX]` | `[0.XX]` | `[0.XX]` |
| **XGBoost** | `[XX.X%]` | `[0.XX]` | `[0.XX]` | `[0.XX]` | `[0.XX]` |

## Tech Stack
`Python` · `Scikit-Learn` · `XGBoost` · `Pandas` · `NumPy` · `Matplotlib / Seaborn`

## Author
**Nahid Ameen** — MSc Cybersecurity Candidate (Anglia Ruskin University) | eCPPT
