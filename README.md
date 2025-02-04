# 📚 Atlanticbooks.com Data Analysis & Dashboard
This repository contains a comprehensive end-to-end data pipeline project that involves web scraping book data from Atlantic Books, cleaning and preprocessing the data, and performing exploratory data analysis (EDA) to gain insights. The data is then loaded into a MySQL database and connected to Power BI for visualization and interactive Power BI dashboards.



## 🚀 Features

✅ Web Scraping: Automated extraction of book details (Fiction, Non-Fiction, Classics) using Selenium.

✅ Data Cleaning: Advanced Pandas operations to handle duplicates, missing values, and data transformations.

✅ MySQL Integration: Robust database design with complex SQL queries for business insights.

✅ Power BI Dashboard: Interactive visualizations showing price trends, category analysis, and publication patterns.

## Technologies Used

* ![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
* [![Selenium](https://img.shields.io/badge/Selenium-43B02A?logo=selenium&logoColor=fff)](#)
* [![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=fff)](#) 
* [![NumPy](https://img.shields.io/badge/NumPy-4DABCF?logo=numpy&logoColor=fff)](#)
* [![Matplotlib](https://custom-icon-badges.demolab.com/badge/Matplotlib-71D291?logo=matplotlib&logoColor=fff)](#)
* ![Seaborn](https://img.shields.io/badge/Seaborn-0.13.2-blue.svg)
* ![MySQL](https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white)
* ![Power BI](https://img.shields.io/badge/PowerBI-F2C811?style=for-the-badge&logo=Power%20BI&logoColor=white)

## ⚙️ Installation

**1️⃣ Install Dependencies**

* pip install selenium pandas sqlalchemy mysql-connector-python matplotlib seaborn

**2️⃣ Required Drivers**

* ChromeDriver (Downloaded and placed in the project root folder, the project root is where our Python scripts are stored)

**3️⃣ Required application**

* mysql-connector-net-8.0.32 (to connect the MySQL with Power BI)

## 📊 Data Pipeline Workflow

**🔹 Step 1: Web Scraping (Atlanticbooks.com Scrapped_EDA_MySQL.ipynb)**

![Image](https://github.com/user-attachments/assets/444187d7-ea37-449d-bd72-e136d9f98647)
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

![Image](https://github.com/user-attachments/assets/3fcb611e-3a5a-41cd-94c2-1496370fea1d)

**🔹 Step 3: MySQL Integration**

* Stores structured data in MySQL for querying.
* Performs price analysis using SQL queries.

**Example SQL Query:**

from tabulate import tabulate

`# Count of books published/year`

`query = """`

`SELECT YEAR(publication_date) AS year, COUNT(*) AS total_books`

`FROM books_data`

`GROUP BY YEAR(publication_date)  -- ✅ Explicitly grouping by YEAR(publication_date)`

`ORDER BY year DESC;`

`"""`

`result_df = pd.read_sql_query(query, engine)`

`# Print result in table format`

`print(tabulate(result_df, headers='keys', tablefmt='psql'))`

|    | year | total_books |
|----|------|--------------|
|  0 | 2025 |           14 |
|  1 | 2024 |           50 |
|  2 | 2023 |          105 |
|  3 | 2022 |           32 |
|  4 | 2021 |           17 |
|  5 | 2020 |           12 |
|  6 | 2019 |           32 |
|  7 | 2018 |           16 |
|  8 | 2017 |            8 |
|  9 | 2016 |            7 |
| 10 | 2015 |            3 |
| 11 | 2014 |            2 |
| 12 | 2013 |            2 |
| 13 | 2012 |            4 |
| 14 | 2010 |            3 |
| 15 | 2009 |            9 |
| 16 | 2008 |            1 |
| 17 | 2006 |            2 |
| 18 | 2000 |            1 |
| 19 | 1994 |            2 |

**🔹 Step 4: Power BI Dashboard**
* Visualizes price distribution, category trends, and discount analysis.
* Provides interactive filters for deep data exploration.

## 📊 Power BI Dashboard Preview**

**🚀 Dashboard Highlights:**

* 📈 Price Trends: Distribution of book prices across categories.

* 📊 Category Popularity: Number of books available per category.

* 🏷 Discount Insights: How much discount is offered across different books.
![Image](https://github.com/user-attachments/assets/5c18ab32-b247-4d10-89b9-00e8a59facd3)

## 🔍 Key Insights

📌 Price Variability: Fiction, Non-Fiction, and Classics have distinct price ranges.

* Fiction books range from ₹94 (Twelfth Night) to ₹1,228 (The Thomas Hardy Collection).

* Non-Fiction books range from ₹94 to ₹1,196 (Capitalism, Socialism and Democracy).

* Classics range from ₹94 to ₹1,122.

📌 Pricing Strategy: Publishers might use penetration pricing to boost sales, especially for collections and classics.

📌 Category Popularity:

* Fiction has the highest number of books.

* Classics and Non-Fiction follow, with Non-Fiction covering diverse subjects like Economics, Sociology, and Health.

## Contact

Prakash Gaurav - [prakashgaurav98@gmail.com](mailto:prakashgaurav98@gmail.com)


