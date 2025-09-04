# Customer Segmentation Analysis using Unsupervised Learning

This repository contains a detailed data science project on customer segmentation for a mall. Using unsupervised machine learning, we analyze customer data to uncover distinct groups, enabling data-driven and targeted marketing strategies that enhance customer engagement and profitability.

## 📋 Table of Contents
- [Executive Summary](#-executive-summary)
- [Project Overview](#-project-overview)
- [Dataset](#-dataset)
- [Methodology](#-methodology)
- [In-Depth Cluster Analysis (k=6)](#-in-depth-cluster-analysis-k6)
- [Future Work and Next Steps](#-future-work-and-next-steps)
- [Key Visualizations](#-key-visualizations)
- [How to Run the Project](#-how-to-run-the-project)
- [Repository Structure](#-repository-structure)

##  Executive Summary
This analysis successfully segmented mall customers into **six distinct personas** using K-Means clustering based on their age, income, and spending score. The most valuable segment identified is the **"Premium Young Spenders"** (young, high-income, high-spending), who should be the primary target for premium offers and loyalty programs.

Conversely, segments like the **"Cautious Rich"** and **"Budget Seniors"** require entirely different strategies focused on value and quality rather than trends. These findings empower the business to move from generic mass marketing to a highly efficient, personalized, and data-driven approach.

## 📖 Project Overview
In today's competitive retail landscape, understanding customer behavior is paramount. This project moves beyond a one-size-fits-all marketing approach by leveraging the power of K-Means clustering. By segmenting customers based on their age, annual income, and spending habits, we can identify key personas within the mall's customer base.

The ultimate goal is to provide actionable insights that allow the marketing team to design highly targeted campaigns, personalize offers, and improve overall customer satisfaction and loyalty.

## 💾 Dataset
The analysis is based on the `Mall_Customers.csv` dataset, which includes the following customer attributes:
- **CustomerID**: A unique identifier for each customer.
- **Gender**: The customer's gender (Male/Female).
- **Age**: The customer's age.
- **Annual Income (k$)**: The customer's annual income in thousands of dollars.
- **Spending Score (1-100)**: A proprietary score assigned by the mall based on customer spending behavior.

## 🛠️ Methodology
The project was executed through a systematic data science workflow:

1.  **Exploratory Data Analysis (EDA)**:
    - **Initial Analysis**: The dataset was found to be clean with no missing values.
    - **Demographics**: The gender distribution is fairly balanced, with **56% Female** and **44% Male** customers.
    - **Distributions**: Histograms revealed that the customer base is diverse, with a notable concentration of younger customers (20-40 years) and a wide range of incomes and spending scores.
    - **Correlations**: A heatmap showed weak linear correlations between the features, indicating that a non-linear clustering algorithm like K-Means is a suitable choice.

2.  **Data Preprocessing**:
    - **Feature Selection**: The `CustomerID` column was dropped as it serves only as an identifier.
    - **Encoding**: The categorical `Gender` feature was converted to a numerical format (`Female`: 0, `Male`: 1) using `LabelEncoder`.
    - **Feature Scaling**: To prevent features with larger scales (like Annual Income) from dominating the clustering process, all relevant features (`Age`, `Annual Income`, `Spending Score`) were standardized using `StandardScaler`, which transforms the data to have a mean of 0 and a standard deviation of 1.

3.  **Model Selection and Optimization**:
    - **Algorithm Comparison**: Three popular clustering algorithms were evaluated: **K-Means**, **Hierarchical Clustering**, and **Gaussian Mixture Models (GMM)**.
    - **Finding Optimal `k`**: The optimal number of clusters (`k`) was determined by:
        - **The Elbow Method**: Plotting the Within-Cluster Sum of Squares (WCSS) against `k` showed a distinct "elbow" at **k=4**, suggesting it as a viable option.
        - **Silhouette Score**: This metric, which measures both cluster cohesion and separation, was calculated for `k` values from 2 to 10. The score peaked at **k=6 (0.428)**, indicating it as the most robust segmentation.
    - **Final Model**: Based on the higher Silhouette Score, **K-Means with k=6** was selected as the final model for its ability to produce more granular and well-defined clusters.

## 🎯 In-Depth Cluster Analysis (k=6)
The K-Means model with 6 clusters provides a nuanced view of the customer base. Below is a detailed breakdown of each segment, including actionable marketing strategies.

| Cluster | Persona                  | Characteristics                                      | Actionable Marketing Strategies                                                                        |
|---------|--------------------------|------------------------------------------------------|--------------------------------------------------------------------------------------------------------|
| **0**   | **Average Older Customers**| Older, with moderate income and average spending.    | - **Strategy**: Focus on building community and trust.<br>- **Actions**: Host in-store workshops (e.g., gardening, crafts), offer loyalty points on reliable brands, market via traditional media. |
| **1**   | **Young Middle-Class**   | Younger, with average income and spending habits.    | - **Strategy**: Engage on their preferred digital platforms.<br>- **Actions**: Run targeted ads on Instagram/TikTok, collaborate with mid-tier influencers, promote seasonal trends. |
| **2**   | **Cautious Rich**        | Older, high-income individuals who spend very little.| - **Strategy**: Emphasize quality, durability, and long-term value.<br>- **Actions**: Send detailed email newsletters about product craftsmanship, offer private viewings for luxury goods. |
| **3**   | **Premium Young Spenders** | Young, high-income, and high-spending. **(Target)**  | - **Strategy**: Treat them as VIPs to maximize their lifetime value.<br>- **Actions**: Exclusive access to new collections, personal shopper services, premium loyalty tiers with experiential rewards. |
| **4**   | **Impulse Buyers**       | Young, low-income, but high-spending.                | - **Strategy**: Create a sense of urgency and excitement.<br>- **Actions**: Use flash sales and limited-time offers, target with visually appealing ads for trendy items, offer "Buy Now, Pay Later" options. |
| **5**   | **Budget Seniors**       | Older, low-income, and highly frugal.                | - **Strategy**: Focus on affordability and practicality.<br>- **Actions**: Promote discounts, bundle deals on essential goods, and communicate via in-store flyers or local newspapers. |

## 🔮 Future Work and Next Steps
This project provides a strong foundation for customer analytics. Future enhancements could include:

- **Integrate Transactional Data**: Incorporate purchase history (e.g., products bought, frequency, ticket size) to create even more granular, behavior-based segments.
- **Develop a Predictive Model**: Build a classification model (e.g., Random Forest, Gradient Boosting) to automatically assign new customers to a segment upon sign-up.
- **Create an Interactive Dashboard**: Develop a dashboard (using tools like Tableau or Power BI) to allow the marketing team to interactively explore the customer segments and their characteristics.
- **A/B Test Marketing Campaigns**: Design and execute A/B tests for the proposed marketing strategies to empirically measure their impact on engagement and sales for each segment.

## 📊 Key Visualizations
Visualizations were critical in understanding the data and the final cluster formations.

#### 1. Cluster Distribution (Income vs. Spending)
This 2D scatter plot is key to understanding the financial behavior of the segments. You can generate this from the notebook.
*(Suggestion: Save the "K=6 Clusters (Income vs Spending)" plot from your notebook as `income_vs_spending_k6.png` and place it in an `assets` folder.)*
`![Income vs Spending Clusters](assets/income_vs_spending_k6.png)`

#### 2. 3D Cluster Visualization
The 3D plot provides a holistic view, incorporating the `Age` dimension, which clearly separates the younger and older segments.
*(Suggestion: Save the "KMeans Clustering (k=6)" 3D plot as `3d_clusters_k6.png` and place it in an `assets` folder.)*
`![3D Clusters](assets/3d_clusters_k6.png)`

#### 3. Elbow Method for Optimal K
This plot shows the WCSS decreasing as `k` increases, with an "elbow" indicating where the rate of decrease slows.
*(Suggestion: Save the "Elbow Method" plot as `elbow_method.png` and place it in an `assets` folder.)*
`![Elbow Method](assets/elbow_method.png)`

## 🚀 How to Run the Project

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/your-username/Customer-Segmentation.git
    cd Customer-Segmentation
    ```

2.  **Create a Virtual Environment (Recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install Dependencies:**
    Install the required libraries using the `requirements.txt` file.
    ```bash
    pip install -r requirements.txt
    ```

4.  **Launch Jupyter Notebook:**
    Run the analysis by opening the `customer_segmentation.ipynb` notebook.
    ```bash
    jupyter notebook notebooks/customer_segmentation.ipynb
    ```

## 📁 Repository Structure
```
Customer-Segmentation/
├── data/
│   └── Mall_Customers.csv          # The raw dataset
├── notebooks/
│   └── customer_segmentation.ipynb # Main Jupyter Notebook with all analysis
├── src/
│   └── clustering.py               # Optional script for clustering functions
├── requirements.txt                # List of Python dependencies
└── README.md                       # Project documentation (this file)
```