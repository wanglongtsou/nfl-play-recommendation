# nfl-play-recommendation
Machine learning model that recommends optimal NFL offensive play calls based on defensive alignment and game context.

# 🏈 NFL Play Recommendation Engine

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Scikit-Learn](https://img.shields.io/badge/ML-Scikit--Learn-green)
![BigQuery](https://img.shields.io/badge/Data-Google%20BigQuery-yellow)
![Status](https://img.shields.io/badge/Status-Production--Ready-brightgreen)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

## 🚀 Overview

This project builds a **machine learning-powered decision engine** that recommends the optimal **offensive play call** based on defensive alignment and game context.

Instead of analyzing plays after the fact, this system answers a forward-looking question:

> **“Given this defense, what play should we call right now?”**

---

## 🎯 Key Features

* Predicts **probability of play success** across multiple play types
* Recommends the **highest expected-value play**
* Incorporates **defensive fronts, coverage schemes, and situational context**
* Built on real NFL data from the Big Data Bowl

---

## 🧠 Methodology

### Problem Framing

* **Type:** Supervised classification
* **Objective:** Maximize probability of offensive success
* **Target Variable:** `play_success`

Success is defined as:

* 1st down → ≥ 45% of yards gained
* 2nd down → ≥ 60%
* 3rd/4th down → 100% (conversion)

---

### Feature Engineering

Key features include:

* Defensive front (e.g., 4-3, 3-4)
* Coverage scheme
* Box count (run defense indicator)
* Down & distance
* Field position

Categorical variables are encoded for model compatibility.

---

### Model

* Baseline: Logistic Regression / Classification model
* Evaluated using:

  * Accuracy
  * Precision / Recall
  * Interpretability of coefficients

---

### Recommendation Logic

For a given defensive scenario:

1. Simulate all possible offensive play types
2. Predict success probability for each
3. Select the play with the highest expected success

---

## 📊 Example Use Case

**Input:**

* Defense: 4-3
* Box: 8 defenders
* Down: 2nd & 7

**Output:**

* Run → 42% success
* Short Pass → 61% success
* Deep Pass → 48% success

✅ **Recommended Play: Short Pass**

---

## 🗂️ Project Structure

```id="n9p3m1"
.
├── nfl_play_recommendation.ipynb   # End-to-end pipeline (EDA → modeling → recommendations)
├── README.md                      # Documentation
```
## Data

This project uses the NFL Big Data Bowl dataset.

Due to file size, data is not included in this repository.

To use this project:
1. Download the dataset from Kaggle or BigQuery
2. Place it in:
   nfl_big_data_bowl_2023/
---

## ⚙️ Tech Stack

* **Python**
* **pandas / numpy** (data processing)
* **scikit-learn** (modeling)
* **Google BigQuery** (data source)

---

## ▶️ How to Run

```bash id="p7k2d1"
pip install pandas numpy scikit-learn google-cloud-bigquery
jupyter notebook nfl_play_recommendation.ipynb
```

---

## 📈 Key Insights

* **Heavy box defenses → passing becomes more efficient**
* **Light fronts → run game gains value**
* Coverage schemes significantly shift optimal play selection

This highlights how **defensive structure directly impacts offensive strategy**.

---

## ⚠️ Limitations

* No player-level tracking data (routes, speed, separation)
* Static model (not updated in real-time)
* Assumes historical trends persist

---

## 🔮 Future Improvements

* Integrate player tracking data
* Upgrade to **XGBoost / ensemble models**
* Deploy as a **real-time decision tool (API or Streamlit app)**
* Incorporate game clock and score dynamics

---

## 📌 Why This Project Matters

This project demonstrates:

* Translating raw sports data into **actionable decisions**
* Combining **domain knowledge + machine learning**
* Building systems that go beyond analysis → **recommendation engines**

---

## 👤 Author

**David Wang**
Associate Banker @ East West Bank
MS Applied Analytics Candidate, Boston College

---

## ⭐ Takeaway

A practical example of how data science can move from **descriptive analytics → prescriptive decision-making** in real-world scenarios.
