# Online Retail II: Market-Basket & Sequential Pattern Mining

## 📖 Overview
This repository contains a single, fully-run Python notebook (`.ipynb`) for a data mining course project checkpoint. The project uses the **Online Retail II** dataset (UCI) to study customer purchasing behavior through:

- **Frequent Itemset Mining & Association Rules (course technique)** using invoice-level baskets  
- **Sequential Pattern Mining (beyond-course technique)** using time-ordered purchases per customer

The notebook focuses on dataset selection, data cleaning, exploratory data analysis (EDA), and initial project direction.

## 📂 Contents
- `project_checkpoint_1.ipynb` — the only file in this repository (run end-to-end)

## 🧠 Project Goals
1. Convert raw transaction logs into **basket data** (each invoice = one basket of items).
2. Discover **frequent itemsets** and generate **association rules** to understand co-purchase patterns.
3. Prepare customer timelines to enable **sequential pattern mining** and compare sequence-based patterns vs. unordered baskets.

## 🔎 Dataset
**Online Retail II (UCI Machine Learning Repository)**  
- 1,067,371 rows across two sheets (2009–2010 and 2010–2011)  
- Key columns: `Invoice`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `Price`, `Customer ID`, `Country`  
- License: **CC BY 4.0**

## 🧹 Data Cleaning Decisions (High-Level)
The notebook includes a documented cleaning pipeline with sanity checks/tests. Main decisions include:
- Dropping missing `Customer ID` (required to build purchase sequences)
- Removing cancellations (invoices starting with `C`)
- Filtering out non-positive `Quantity`
- Filtering out non-positive `Price`

## 📊 EDA Highlights (What the Notebook Measures)
- Basket size distribution (including long-tail large orders)
- Most frequent items (head of the product distribution)
- Global sparsity of the invoice–item matrix
- Temporal gaps between customer visits to verify feasibility of sequential mining

## ⚙️ How to Run
1. Download the **Online Retail II** Excel file from UCI.
2. Update the notebook’s `FILE_PATH` to point to your local `.xlsx`.
3. Run all cells top-to-bottom.

Recommended environment:
- Python 3.10+
- pandas, numpy, matplotlib, seaborn

## 📌 Initial Research Questions
- How does the **support threshold** change the quality of association rules (lift/confidence), especially in the long tail?
- Do **sequential patterns** capture behavior that association rules miss, especially for product categories where order matters?

## 🧾 Collaboration Declaration
**Collaborators:** None  

**Web Sources / Datasets:**
- Chen, D. (2012). *Online Retail II* [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5CG6D  
- GroupLens. *MovieLens 32M* dataset page. https://grouplens.org/datasets/movielens/32m/  
- Machine Learning Group – ULB. *Credit Card Fraud Detection* [Dataset]. Kaggle. https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud  

**Papers:**
- Harper, F. M., & Konstan, J. A. (2015). *The MovieLens Datasets: History and Context.* ACM TiiS. https://doi.org/10.1145/2827872  
- Dal Pozzolo, A., Caelen, O., Johnson, R. A., & Bontempi, G. (2015). *Calibrating Probability with Undersampling for Unbalanced Classification.* IEEE CIDM.

**AI Tools:**
- Google Gemini — used for coding help and proofreading (final decisions and validation done manually).

## ⚠️ Notes
- The dataset contains potentially sensitive purchase behavior. Results should be reported **in aggregate** and should avoid attempting to identify individuals or businesses.
- The notebook includes basic tests (assertions) to validate non-trivial cleaning and grouping behavior.