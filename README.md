# Big Data Analytics & Machine Learning Projects

**Executive Summary:** This repository contains Python-based ETL pipelines and predictive machine learning models built for Big Data Analytics (SOEN-471).

## Tech Stack Used
* **Python**
* **Jupyter Notebook**
* **Pandas**
* **NumPy**
* **Scikit-Learn**

## Data Pipeline (ETL)
To ensure the machine learning models receive high-quality inputs, the notebooks in this repository follow a rigorous data engineering workflow:
* **Extract:** Raw data is ingested directly from static CSV files, including streaming customer subscription records, e-commerce user interaction logs, and product catalogs.
* **Transform:** Data is cleaned and reshaped using Pandas. Key transformations include dropping non-predictive identifiers, handling missing data (e.g., zero-filling sparse user-item matrices), encoding categorical variables (One-Hot Encoding), and aggregating multi-category user behaviors into normalized structures.
* **Load / Analyze:** The transformed, model-ready datasets are loaded into Scikit-Learn and MLxtend memory structures to train predictive classifiers (Decision Trees, Random Forests), compute Cosine Similarities for collaborative filtering, and execute Apriori pattern mining.

## Projects in this Repository

### [Assignment 1: Customer Churn Prediction Engine](https://github.com/NathanGrenier/SOEN-471/tree/main/a1)
A machine learning project that predicts whether a streaming service customer will cancel their subscription ("churn"). 
* **Business Value:** Enables targeted marketing interventions by identifying at-risk customers and isolating the key metrics driving cancellations.

### [Assignment 2: E-Commerce Recommender System & Pattern Mining](https://github.com/NathanGrenier/SOEN-471/tree/main/a2)
An analytics project that builds a personalized product recommendation engine and discovers natural product bundles from user transaction data.
* **Business Value:** Increases e-commerce conversion rates through targeted recommendations and optimizes cross-selling via market basket analysis.