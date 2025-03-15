# CodeAlpha_Exploratory-Data-Analysis-EDA

This repository contains a detailed Exploratory Data Analysis (EDA) of a retail sales dataset. The analysis includes data cleaning, statistical summaries, visualizations, and insights to understand sales trends, customer behavior, and product performance.

📂 Folder Structure:
EDA_Retail_Sales_Analysis/
│-- 📄 README.md
│-- 📂 data/
│   │-- retail_sales_dataset.csv
│-- 📂 notebooks/
│   │-- EDA_Retail_Sales.ipynb
│-- 📂 reports/
│   │-- EDA_Report.pdf
│-- 📂 visuals/
│   │-- correlation_heatmap.png
│   │-- sales_distribution.png
│-- 📂 scripts/
│   │-- data_cleaning.py
│   │-- visualization.py

📊 Key Features:
✅ Data Cleaning & Preprocessing: Handling missing values, duplicates, and outliers.
✅ Statistical Summaries: Understanding mean, median, standard deviation, and correlations.
✅ Data Visualizations: Using Seaborn & Matplotlib for histograms, bar charts, and heatmaps.
✅ Feature Analysis: Checking gender distribution, product category performance, and sales trends.
✅ Insights & Recommendations: Identifying business opportunities and areas for improvement.

📌 Technologies Used:
🔹 Python (Pandas, NumPy, Seaborn, Matplotlib)
🔹 Jupyter Notebook
🔹 GitHub for version control


Step	Description	Code Used	Graph/Output
1. Load Data	Load the CSV file	df = pd.read_csv(file_path, encoding="latin1")	N/A
2. Data Overview	Get basic information about the dataset	df.info()	Data Types & Missing Values
3. First 5 Rows	View the first few rows of data	df.head()	Top 5 Rows of Data
4. Shape of Data	Check total number of rows and columns	df.shape	(Rows, Columns) Count
5. Columns List	Display column names	df.columns.tolist()	Column Names
6. Missing Values	Check missing data in each column	df.isnull().sum()	Missing Values Count
7. Statistical Summary	Summary of numerical data	df.describe()	Mean, Std Dev, Min, Max, etc.
8. Unique Values	Count unique values in categorical columns	df[col].nunique()	Unique Values Count
9. Filling Missing Data	Fill missing numerical & categorical data	df.fillna(df.mean()), df.fillna("Unknown")	N/A
10. Outliers Detection	Detect outliers using boxplot	sns.boxplot(data=df.select_dtypes(include=[np.number]))	📊 Boxplot
11. Correlation Matrix	Check relationships between columns	sns.heatmap(df.corr(), annot=True, cmap="coolwarm")	🔥 Heatmap
12. Gender Distribution	Analyze Male/Female customer ratio	sns.countplot(x="Gender", data=df, hue="Gender", palette="pastel", legend=False)	📊 Bar Chart
13. Product Category Analysis	Identify the most sold product category	sns.countplot(x="Product Category", data=df, palette="muted")	📊 Bar Chart
14. Sales Distribution	Analyze the distribution of sales	sns.histplot(df["Sales"], bins=30, kde=True, color="blue")	📊 Histogram
15. Feature Correlation (Bar Chart)	Show how features correlate with sales	df.corr()["Sales"].drop("Sales").sort_values().plot(kind="barh")	📊 Bar Chart

✅ 1. Data Structure
Rows: 1000
Columns: 6

✅ 2. Column Details
Column Name	Data Type
Date	Object (Categorical)
Customer ID	Object (Categorical)
Gender	Object (Categorical)
Product Category	Object (Categorical)
Sales	Float64 (Numerical)
Quantity	Int64 (Numerical)

📌 Meaning: Your dataset contains both categorical and numerical columns.

✅ 3. Missing Values Check
Column Name	Missing Values (NaN)
Date	0
Customer ID	0
Gender	0
Product Category	0
Sales	0
Quantity	0

✅ No missing values found! 🎉

✅ 4. Numerical Data Summary Statistics
Metric	Sales	Quantity
Mean (Average)	497.27	5.01
Min (Minimum)	20.50	1
Max (Maximum)	999.00	10
Standard Deviation (Std)	289.73	2.88

📌 Meaning:
The average sales value is 497.27.
The maximum sales value is 999.00, while the minimum is 20.50.
Standard deviation is 289.73, indicating a large variation in sales values.

✅ 5. Categorical Data Analysis

🔹 Gender Distribution (Male vs Female Customers)
Female Customers: 510
Male Customers: 490

🔹 Product Category Distribution
Clothing: 351
Electronics: 342
Beauty: 307

📌 Meaning:

Clothing has the highest sales among all product categories.
The number of male and female customers is almost equal.
