# Customer Segmentation Analysis

![Python](https://img.shields.io/badge/Python-3.12-blue.svg)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

This repository contains a data science project focused on segmenting mall customers using K-Means clustering. The goal is to uncover distinct customer personas to enable targeted and effective marketing.

## 📋 Table of Contents
- [Project Overview](#-project-overview)
- [Key Findings](#-key-findings)
- [Visualizations](#-visualizations)
- [Getting Started](#-getting-started)
- [Contributing](#-contributing)
- [License](#-license)
- [Contact](#-contact)

## 📖 Project Overview
This project moves beyond a one-size-fits-all marketing approach by leveraging unsupervised machine learning. By analyzing customer age, income, and spending score, we identify key groups within the mall's customer base. The complete analysis, including the exploratory data analysis (EDA) and model development, is detailed in the [customer_segmentation.ipynb](./notebooks/customer_segmentation.ipynb) notebook.

## 🎯 Key Findings
The analysis successfully segmented customers into **six distinct personas**. These groups provide a clear roadmap for targeted marketing. The most valuable segments include:

- **Premium Young Spenders (Target Group)**: Young, high-income, high-spending individuals. Ideal for VIP programs and exclusive offers.
- **Impulse Buyers**: Young, low-income but high-spending. Best targeted with trend-based marketing and time-sensitive sales.
- **Cautious Rich**: Older, high-income but low-spending. Require marketing focused on quality, value, and durability.

> For a full breakdown of all six segments and their recommended marketing strategies, please see the analysis in the [Jupyter Notebook](./notebooks/customer_segmentation.ipynb).

## 📊 Visualizations
Key visualizations from the notebook that summarize the results:

#### 1. 3D Cluster Visualization
A holistic view of the segments across Age, Income, and Spending Score.
`![3D Clusters](assets/3d_clusters_k6.png)`

#### 2. Income vs. Spending Clusters
A 2D plot showing the clear financial separation between the identified clusters.
`![Income vs Spending Clusters](assets/income_vs_spending_k6.png)`


## 🚀 Getting Started

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/your-username/Customer-Segmentation.git
    cd Customer-Segmentation
    ```

2.  **Install Dependencies:**
    It is recommended to use a virtual environment.
    ```bash
    pip install -r requirements.txt
    ```

3.  **Run the Analysis:**
    Launch the Jupyter Notebook to explore the full project.
    ```bash
    jupyter notebook notebooks/customer_segmentation.ipynb
    ```

## 🤝 Contributing
Contributions are welcome! If you have suggestions for improving this project, please feel free to open an issue or submit a pull request.

1.  **Fork the Project**
2.  **Create your Feature Branch** (`git checkout -b feature/AmazingFeature`)
3.  **Commit your Changes** (`git commit -m 'Add some AmazingFeature'`)
4.  **Push to the Branch** (`git push origin feature/AmazingFeature`)
5.  **Open a Pull Request**

## 📄 License
This project is distributed under the MIT License. See the `LICENSE` file for more information.

## 📧 Contact
**Author**: [Narender Singh](https://github.com/Narendersingh007)  

**Project Link**: [Customer Segmentation](https://github.com/Narendersingh007/customer-segmentation)
