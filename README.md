# SIEM Anomaly Detection with Isolation Forest

This project implements an AI-based anomaly detection system for security information and event management (SIEM) logs using the Isolation Forest algorithm. It is designed to identify suspicious activities or anomalies in log data by learning the normal patterns and isolating the outliers.

---

## Overview

Security logs often contain a large amount of unstructured and noisy data. Manually identifying anomalies is impractical, especially in large enterprise environments. This project uses machine learning to:
- Automatically identify unusual patterns or events
- Visualize the separation of normal vs. anomalous log entries
- Help analysts quickly focus on high-risk events

---

## Features

- **Unsupervised learning** with the Isolation Forest algorithm
- **Log preprocessing and feature engineering**
- **Anomaly scoring and thresholding**
- **Dimensionality reduction (optional) using PCA or t-SNE**
- **Visualizations** of anomalies and feature distributions
- **Evaluation of anomaly thresholds**
- **Extensible and modular notebook-based code**

---

## Data

The project uses a CSV file (`sample_logs.csv`) containing anonymized SIEM-like log data.

| timestamp           | src\_ip     | dest\_ip   | protocol | status\_code | bytes\_sent | action |
| ------------------- | ----------- | ---------- | -------- | ------------ | ----------- | ------ |
| 2023-05-01 10:05:23 | 192.168.1.5 | 172.16.0.8 | TCP      | 200          | 304         | allow  |


Preprocessing includes:
- Encoding categorical values
- Converting timestamps
- Scaling numerical features

---

## Anomaly Detection Algorithm

### Isolation Forest
Isolation Forest isolates anomalies instead of profiling normal data. It works by:
1. Randomly selecting a feature and split value.
2. Creating trees that isolate data points.
3. Scoring anomalies by how quickly they are isolated.

Anomalies are easier to isolate and therefore have **shorter path lengths** in the tree.

---

## Installation

You need Python 3.7+ and the following libraries:

```bash
pip install numpy pandas scikit-learn matplotlib seaborn jupyter

