# 🔥 Big Data Marketing Analytics with Apache Spark

> **Academic Project | Big Data for Marketing | NOVA IMS 2026**  
> Real-world marketing analytics simulation using PySpark — from raw data to real-time insights

---

## 📌 Project Overview

This project simulates a **real-world marketing data consulting engagement**, where our team acts as data scientists delivering analytical prototypes and management-ready insights for a retail client.

We demonstrate how **Apache Spark** can be used at scale to transform, analyse, and extract value from large marketing datasets — covering the full pipeline from raw data ingestion to real-time streaming dashboards.

---

## 🏗️ Architecture

```
Raw Data (1M+ rows)
        ↓
Data Cleaning & Quality (RDDs + DataFrames)
        ↓
Marketing Analysis (SparkSQL)
        ↓
Feature Engineering (RFM + ML Pipelines)
        ↓
Machine Learning (KMeans + Random Forest)
        ↓
Graph Analytics (GraphFrames — Twitch Network)
        ↓
Real-Time Streaming (Structured Streaming)
```

---

## 📂 Repository Structure

```
├── notebooks/
│   ├── 01_EDA_RDDs.ipynb                    # Data loading, cleaning, RDD operations
│   ├── 02_DataFrames_SparkSQL.ipynb         # SQL analysis, window functions, visualisations
│   ├── 03_ML_Pipeline_Clustering.ipynb      # RFM features, KMeans segmentation, churn prediction
│   ├── 04_GraphFrames.ipynb                 # Twitch network analysis — PageRank, BFS, motifs
│   └── 05_Streaming.ipynb                   # Real-time transaction processing
├── presentation/
│   └── BigData_Marketing_Presentation.pdf   # Management-ready slides
├── data/
│   └── README.md                            # Dataset download instructions
└── README.md
```

---

## 📊 Datasets

| Dataset | Source | Size | Used For |
|---|---|---|---|
| Online Retail II | UCI ML Repository | 1,067,371 rows | Core analysis, ML, Streaming |
| Twitch Social Network | Stanford SNAP | 168,114 nodes, 6.8M edges | GraphFrames analysis |

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **Apache Spark 3.5** | Distributed data processing |
| **PySpark** | Python API for Spark |
| **Spark MLlib** | Distributed machine learning |
| **GraphFrames** | Graph analytics |
| **Spark Structured Streaming** | Real-time processing |
| **SparkSQL** | SQL on distributed data |
| **Matplotlib** | Visualisations |
| **Lightning.ai** | Cloud compute environment |

---

## 🔍 Key Features Demonstrated

### 1. RDDs — Spark Internals
- `map`, `flatMap`, `filter`, `reduceByKey`, `sortBy`
- MapReduce pattern explicitly demonstrated
- `reduceByKey` vs `groupByKey` — big data safety explained
- Pareto analysis: 261 customers = 50.2% of £17.3M revenue

### 2. DataFrames & SparkSQL
- Revenue by country, product, and time period
- Window functions: `RANK()`, `DENSE_RANK()`, `LAG()`
- `PARTITION BY` for parallel country-level analysis
- Month-over-month growth calculations

### 3. ML Pipelines & Feature Engineering
- RFM (Recency, Frequency, Monetary) feature engineering
- `VectorAssembler` → `StandardScaler` → model
- Why Pipeline prevents data leakage in distributed systems
- Outlier analysis and justified decision to retain Champions segment

### 4. Machine Learning
- **KMeans Clustering** — 4 customer segments identified
  - Champions (4 customers, avg £428k spend)
  - High Value (35 customers, avg £81k spend)
  - Loyal Customers (3,842 customers)
  - Hibernating/Lost (1,997 customers)
- **Random Forest Churn Prediction** — AUC 0.9997
- Feature importance analysis
- Elbow method for optimal k selection
- Silhouette score evaluation

### 5. GraphFrames — Twitch Network Analysis
- **PageRank** — identify most influential streamers
- **Connected Components** — discover communities
- **Motif Finding** — mutual follow partnerships
- **Shortest Paths** — content propagation distance
- **BFS** — path from top influencer to target audience
- **Triangle Count** — measure community cohesion
- Memory limitation handling with justified graph sampling

### 6. Structured Streaming (Bonus)
- Real-time revenue dashboard by country
- High-value transaction alerts (>£500)
- Live single-transaction demo
- Two output modes: `complete` and `append`

---

## 💡 Key Marketing Insights

```
1. Top 261 customers (4.4%) generate 50.2% of total revenue
   → Prioritise VIP retention programmes

2. Champions segment: 4 customers averaging £428,612 each
   → Likely B2B wholesale — requires dedicated account management

3. 1,997 customers haven't purchased in 463+ days
   → Win-back campaign opportunity with targeted discounts

4. Twitch network: top influencer PageRank score 31.84
   → Exponentially more reach than average streamer

5. Real-time streaming detects high-value purchases instantly
   → Enables same-day VIP outreach vs overnight batch delays
```

---

## 🚀 How to Run

### Prerequisites
```bash
pip install pyspark==3.5.0 graphframes-py==0.10.0 openpyxl matplotlib pandas
```

### Environment Setup
```python
from pyspark.sql import SparkSession

spark = SparkSession.builder \
    .appName("BigDataMarketing") \
    .config("spark.jars.packages", "io.graphframes:graphframes-spark3_2.12:0.10.0") \
    .getOrCreate()
```

### Data Download
- **Online Retail II**: [UCI ML Repository](https://archive.ics.uci.edu/dataset/502/online+retail+ii)
- **Twitch Network**: [Stanford SNAP](https://snap.stanford.edu/data/twitch_gamers.html)

### Run Notebooks
Execute notebooks in order: `01` → `02` → `03` → `04` → `05`

---

## 📈 Big Data Safety Practices

Throughout this project we explicitly follow big data best practices:

- ✅ `orderBy()` with explicit direction (never implicit `sort()`)
- ✅ `reduceByKey` over `groupByKey` (partial aggregation first)
- ✅ `broadcast()` joins for small lookup tables
- ✅ `cache()` for DataFrames used multiple times
- ✅ Explicit schema definition for streaming
- ✅ Pipeline for consistent distributed preprocessing
- ⚠️ All non-big-data-safe operations flagged with comments

---

## 👥 Team

**Group 12 — NOVA IMS Big Data for Marketing 2026**

---

## 📄 License

This project is for academic purposes — NOVA IMS Big Data for Marketing course.

---

## ⭐ If you found this useful, give it a star!
