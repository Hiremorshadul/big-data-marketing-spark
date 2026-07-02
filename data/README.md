# 📊 Datasets Instructions

This directory contains instructions on how to download and place the datasets required for running the notebooks in this repository.

Due to GitHub file size limits, the raw datasets themselves are excluded from version control using `.gitignore`. They must be downloaded and placed directly inside the `data/` directory before running the notebooks.

---

## 🛍️ 1. Online Retail II Dataset

- **Used In**: 
  - `01_EDA_RDDs.ipynb`
  - `02_DataFrames_SparkSQL.ipynb`
  - `03_ML_Pipeline_Clustering.ipynb`
  - `05_Streaming.ipynb`
- **Source URL**: [UCI Machine Learning Repository — Online Retail II](https://archive.ics.uci.edu/dataset/502/online+retail+II)
- **Direct Download Link**: [online_retail_II.xlsx (45.6 MB)](https://archive.ics.uci.edu/ml/machine-learning-databases/00502/online_retail_II.xlsx)
- **Required Filename**: `online_retail_II.xlsx`
- **Description**: 
  This dataset contains all transactions occurring between 01/12/2009 and 09/12/2011 for a UK-based and registered non-store online retail. The company mainly sells unique all-occasion giftware. Many customers of the company are wholesalers.
- **Schema Columns**:
  - `Invoice`: Invoice number (6-digit integral number, starts with 'C' for cancellation)
  - `StockCode`: Product code (5-digit integral number)
  - `Description`: Product name
  - `Quantity`: Quantities of each product per transaction
  - `InvoiceDate`: Invoice date and time
  - `Price`: Unit price
  - `Customer ID`: Customer number (5-digit integral number)
  - `Country`: Country name

---

## 🎮 2. Twitch Gamers Social Network Dataset

- **Used In**: 
  - `04_GraphFrames.ipynb`
- **Source URL**: [Stanford SNAP — Twitch Gamers Social Network](https://snap.stanford.edu/data/twitch_gamers.html)
- **Required Files**:
  1. **Edges Link**: [large_twitch_edges.csv (86.2 MB)](https://snap.stanford.edu/data/twitch_gamers.zip) (Extracted from the zip)
  2. **Features Link**: [large_twitch_features.csv (8.0 MB)](https://snap.stanford.edu/data/twitch_gamers.zip) (Extracted from the zip)
- **Required Filenames**: `large_twitch_edges.csv` and `large_twitch_features.csv`
- **Description**: 
  A social network of Twitch users collected from the public API in Spring 2018. Nodes represent Twitch users (vertices) and edges represent mutual follower relationships between them.
- **Node Features**:
  - `views`: Total channel views
  - `life_time`: Streamer life time in days
  - `mature`: Mature content flag (binary)
  - `dead_1`: Dead account flag (binary)
  - `language`: Primary streaming language
  - `affiliate`: Affiliate status flag (binary)
  - `numeric_id`: Unique identifier for each node
- **Edge Connections**:
  - `numeric_id_1`: Source user ID
  - `numeric_id_2`: Destination user ID
