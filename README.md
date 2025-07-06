# CS610 Group 18 · RT-IoT 2022 Intrusion-Detection Project
Applied Machine Learning – April 2025 term  
Singapore Management University (SMU)

![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)
![License](https://img.shields.io/badge/Data%20License-CC%20BY%204.0-green.svg)

---

## 1. Project Overview
Internet-of-Things (IoT) devices dramatically expand an organisation’s attack surface, yet most
enterprise IDS solutions are still tuned for classic IT traffic.  
Our goal in this project is to **benchmark both traditional ML models and modern deep-learning
approaches on a purpose-built IoT network-traffic dataset** and to understand:

* How well “standard” tabular models (e.g. XGBoost, Random Forest) generalise to IoT traffic  
* Whether deep-learning architectures such as TabNet offer a measurable improvement  

---

## 2. Dataset: **RT-IoT 2022**
* **Source:** UCI Machine Learning Repository (ID 942) – “RT-IoT 2022”
* **Records:** ≈ 209 k flows, 83 features  
* **Classes:** 9 distinct attack types + benign traffic (MQTT, ThingSpeak-LED, Wipro-Bulb, Alexa)  
* **License:** Creative Commons Attribution 4.0 (CC BY 4.0)

> **Why we chose it:**  
> The dataset contains realistic smart-home devices and low-footprint attacks (Nmap scans,
> ARP-poisoning, Slowloris) that represent real risks yet are rarely covered in older corpora such as
> KDD’99 or CICIDS2017.

---

## 3. Repository Structure

| Path | Purpose |
|------|---------|
| `binaryclass_models.ipynb` | Feature engineering pipeline + classic binary models |
| `binary_classification_xgboost_performance_sanity_checks.ipynb` | Leakage checks & A/B baselines |
| `multiclass_models.ipynb` | One-vs-rest & native multiclass experiments |
| `multiclass_tabnet.ipynb` | Deep-learning (TabNet) with Optuna tuning |
| `unsupervised_exploration_part1.ipynb` | PCA / UMAP + DBSCAN for anomaly hunting |
| `unsupervised_exploration_part2.ipynb` | Cluster stability & silhouette diagnostics |

---

## 4. Installation and Setup 

To set up the environment:
```
pip install -r requirements.txt
```
We recommend using Jupyter or VS Code with a Python 3.10+ environment.

---

## 5. Usage

You can run the notebooks in the following order:

1. binaryclass_models.ipynb – Builds binary classifiers on attack vs benign
2. binary_classification_xgboost_performance_sanity_checks.ipynb – Validates results and leakage
3. multiclass_models.ipynb – Evaluates performance across 7 attack classes
4. multiclass_tabnet.ipynb – Trains TabNet using Optuna to tune F1-macro
5. unsupervised_exploration_part1/2.ipynb – Optional: clustering on unlabeled flows

---

## 6. Contributors

Developed by Group 18 – CS610 Applied Machine Learning  
Singapore Management University (SMU), 2025

Members: Andres Fernando Garcia Delgado, CHAM Hui Ern Deon, Chen Haoyan, Goh Zhi Ann, Lewis Gordon Keyte
