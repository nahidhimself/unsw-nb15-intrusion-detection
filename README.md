# Network Intrusion Detection System (NIDS) — UNSW-NB15

A supervised machine learning classification pipeline built in Python to evaluate **Logistic Regression**, **Random Forest**, and **XGBoost** for multi-vector network intrusion detection on the **UNSW-NB15** dataset.

## Objectives
- Address class imbalance and high-dimensional network flow features in modern intrusion detection.
- Compare detection performance, false alarm rates (FAR), and recall trade-offs across linear and tree-based ensemble models.
- Map top predictive network flow features (`sttl`, `ct_state_ttl`, `sbytes`, `dbytes`, `sload`) to practical SOC alert triage rules.

## Dataset & Preprocessing
- **Dataset:** UNSW-NB15 (9 attack categories: Fuzzers, Analysis, Backdoors, DoS, Exploits, Generic, Reconnaissance, Shellcode, Worms + Normal traffic).
- **Pipeline:**
  1. Dropped identifier leakage columns (`id`, `attack_cat` for binary classification) and encoded categorical protocol fields (`proto`, `service`, `state`).
  2. Applied stratified train/test splitting to preserve minority attack distributions.
  3. Evaluated models using **Accuracy, Precision, Recall, F1-Score, ROC-AUC, and False Alarm Rate (FAR)** alongside confusion matrices and ROC/PR curves.

## Results Summary
| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC | False Alarm Rate (FAR) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Logistic Regression** | `86.59%` | `0.8372` | `0.9392` | `0.8852` | `0.9664` | `0.2238` |
| **Random Forest** | `87.07%` | `0.8165` | `0.9869` | `0.8936` | `0.9803` | `0.2718` |
| **XGBoost** | `90.87%` | `0.8819` | `0.9633` | `0.9208` | `0.9848` | `0.1581` |

### Key SOC Triage Takeaways
- **XGBoost (Best Overall Balance):** Achieved the highest accuracy (`90.87%`), F1-score (`0.9208`), and ROC-AUC (`0.9848`) while cutting the False Alarm Rate down to `0.1581`—minimizing analyst alert fatigue.
- **Random Forest (Maximum Sensitivity):** Delivered `98.69%` recall (`0.9869`), making it suited for high-security perimeters where missing an intrusion carries higher risk than investigating extra alerts.

## Tech Stack
`Python` · `Scikit-Learn` · `XGBoost` · `Pandas` · `NumPy` · `Matplotlib / Seaborn`

## Author
**Nahid Ameen** — MSc Cybersecurity Candidate (Anglia Ruskin University) | eCPPT
