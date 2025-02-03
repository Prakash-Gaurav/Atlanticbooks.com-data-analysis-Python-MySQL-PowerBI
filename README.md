# 📚 Atlantic Books Data Analysis & Dashboard
This repository contains a comprehensive end-to-end data pipeline project that involves web scraping book data from Atlantic Books, cleaning and preprocessing the data, and performing exploratory data analysis (EDA) to gain insights. The data is then loaded into a MySQL database and connected to Power BI for visualization and interactive Power BI dashboards.

## 🚀 Features

✅ Web Scraping: Automated extraction of book details (Fiction, Non-Fiction, Classics) using Selenium.

✅ Data Cleaning: Advanced Pandas operations to handle duplicates, missing values, and data transformations.

✅ MySQL Integration: Robust database design with complex SQL queries for business insights.

✅ Power BI Dashboard: Interactive visualizations showing price trends, category analysis, and publication patterns.

## Technologies Used

* Python
* Selenium
* Pandas
* NumPy
* Matplotlib
* Seaborn
* MySQL
* Power BI

## ⚙️ Installation

**1️⃣ Install Dependencies**

* pip install selenium pandas sqlalchemy mysql-connector-python matplotlib seaborn

**2️⃣ Required Drivers**

* ChromeDriver (Downloaded and placed in the project root folder, the project root is where our Python scripts are stored)

**3️⃣ Required application**

* mysql-connector-net-8.0.32 (to connect the MySQL with Power BI)

## 📊 Data Pipeline Workflow

**🔹 Step 1: Web Scraping (Atlanticbooks.com Scrapped_EDA_MySQL.ipynb)**
* Uses Selenium for automated extraction of book details.
* Handles pagination and navigates to detailed pages.

**Sample Scraping Code:**

`def scrape_category(category_name):`

    # Selenium automation to extract book data

    pass  # Pagination handling & detailed page navigation logic`

**🔹 Step 2: Data Cleaning (Atlanticbooks.com Scrapped_EDA_MySQL.ipynb.ipynb)**

* Removes duplicates.
* Handles missing values (data imputation).
* Converts data types (Prices, Dates, Weights).
* Conducts outlier analysis using the Interquartile Range (IQR) method.

**📈 Sample Analysis Code**

`import matplotlib.pyplot as plt`

`import seaborn as sns`

`#Showing the Disrtibution of book prices.`

`plt.figure(figsize=(10, 5))`

`sns.histplot(df["price"], bins=20, color="orange", kde=True, line_kws={"color": "red"})`

`plt.title("Distribution of Book Prices")`

`plt.xlabel("Price (INR)")`

`plt.ylabel("Count")`

`plt.grid(axis='y', linestyle='--', alpha=0.7)`

`plt.show()`




