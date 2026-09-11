# 📊 Retail Sales Analysis

### Finding patterns in sales data with Python.

A small exploratory data analysis project built around a simple question:

> **What can a few columns of sales data tell us about how a business is performing?**

This project takes a retail sales dataset, cleans it, explores the relationships between its variables, and turns the raw records into visual insights around **products, regions, time, quantity, pricing, and sales**.

Rather than building a dashboard or predictive model, the focus here is on the foundations of data analysis:

**Understand → Clean → Explore → Visualize → Interpret**

---

## 🗃️ The Data

The dataset contains **3 sample sales records** with the following fields:

```text
Date
OrderID
Product
Category
Region
CustomerID
Quantity
UnitPrice
Sales
```

At first glance, these are just individual transactions.

But when grouped and visualized, they can answer questions such as:

* Which products generate the most sales?
* Which regions contribute the most?
* How does sales activity change over time?
* Are quantity and sales related?
* Are there any missing or duplicate records?

---

## 🔎 From Rows to Insights

The notebook follows this path:

```text
             Raw CSV
                │
                ▼
        ┌───────────────┐
        │  Data Loading │
        └───────┬───────┘
                │
                ▼
        ┌───────────────┐
        │Data Inspection│
        │info / describe│
        └───────┬───────┘
                │
                ▼
        ┌───────────────┐
        │ Data Cleaning │
        │ duplicates /  │
        │ missing values│
        └───────┬───────┘
                │
                ▼
       ┌─────────────────┐
       │    Analysis     │
       ├─────────────────┤
       │ Product Sales   │
       │ Regional Sales  │
       │ Monthly Trends  │
       │ Correlations    │
       └────────┬────────┘
                │
                ▼
       ┌─────────────────┐
       │  Visualization  │
       └─────────────────┘
```

---

## 📌 What I Explored

### 🏆 Product Performance

Products are grouped together and their total sales are calculated.

The notebook then selects the **top 10 products by total sales** and presents them as a bar chart.

This is useful for quickly identifying which products contribute the most to the recorded sales.

---

### 🗺️ Regional Breakdown

If regional information is available, sales are grouped by:

```text
Region → Total Sales
```

A bar chart then makes it easier to compare the contribution of different regions.

Instead of looking through individual transactions, we can see the regional picture at a glance.

---

### 📅 Sales Over Time

The `Date` column is converted into a proper datetime format.

Monthly sales are then calculated and plotted as a line chart:

```text
Daily Transactions
        ↓
     DateTime
        ↓
     Month
        ↓
  Total Sales
        ↓
   Trend Chart
```

This provides a basic view of how sales vary across the available period.

---

### 🔗 Correlation

The notebook also looks at correlations between numerical variables.

The analysis considers fields such as:

```text
Quantity
UnitPrice
Sales
```

and visualizes their correlation matrix using a heatmap.

This is useful for exploring relationships within the dataset before making any assumptions about them.

> **Correlation is an indication of association, not proof of causation.**

---

## 🧹 Before the Analysis

Raw data isn't always ready for analysis.

The notebook performs a few basic cleaning operations:

```python
df = df.drop_duplicates()
df = df.fillna(0)
```

The date field is also converted when available:

```python
df['Date'] = pd.to_datetime(df['Date'])
```

Then the cleaned dataset becomes the basis for the visual analysis.

---

## 📈 The Visual Side

The notebook uses different charts for different questions:

```text
Question                         Visualization

Which products sell most?    →   Bar Chart

Which regions perform best?  →   Bar Chart

How does sales change?       →   Line Chart

How are variables related?  →   Correlation Heatmap
```

The idea is not to create charts simply because the data can be plotted.

Each visualization answers a different analytical question.

---

## 🧪 Notebook Structure

The analysis is contained in:

```text
sales_data_analysis.ipynb
```

The notebook moves through the analysis in a simple sequence:

```text
Load Data
   ↓
Inspect Data
   ↓
Clean Data
   ↓
Analyze Products
   ↓
Analyze Regions
   ↓
Analyze Time
   ↓
Explore Correlations
   ↓
Interpret Results
```

This also makes the notebook useful as a reference for practicing the typical flow of an exploratory data analysis project.

---

## 🛠️ Tools Used

**Python**
The language used for the analysis.

**Pandas**
Used for loading, cleaning, grouping, and manipulating the dataset.

**Matplotlib**
Used to create the visualizations.

**Seaborn**
Used for statistical visualizations, including the correlation heatmap.

**Jupyter Notebook / Google Colab**
Used as the interactive environment for running and documenting the analysis.

---

## 📁 Repository Structure

```text
retail-sales-analysis/
│
├── sales_data.csv
├── sales_data_analysis.ipynb
└── README.md
```

### `sales_data.csv`

The dataset used throughout the analysis.

### `sales_data_analysis.ipynb`

The complete exploratory analysis, including data preparation, calculations, charts, and observations.

---

## ▶️ Run the Analysis

### Option 1 — Google Colab

Open the notebook in Google Colab and run the cells sequentially.

The notebook can also be downloaded and opened locally using Jupyter Notebook or JupyterLab.

### Option 2 — Run Locally

Install the required libraries:

```bash
pip install pandas matplotlib seaborn jupyter
```

Start Jupyter:

```bash
jupyter notebook
```

Then open:

```text
sales_data_analysis.ipynb
```

Make sure `sales_data.csv` is available in the same project directory.

---

## 💡 What Stood Out to Me

One of the useful lessons from this project was realizing that **analysis doesn't start with a chart**.

It starts with understanding the data.

```text
             "What do I have?"
                    ↓
             "Is it clean?"
                    ↓
             "What can I ask?"
                    ↓
             "Which metric?"
                    ↓
             "Which chart?"
                    ↓
             "What does it mean?"
```

That shift — from simply plotting columns to asking questions about the data — is an important part of becoming better at data analysis.

---

## 🔭 What Could Come Next?

This notebook is intentionally an exploratory starting point.

With a larger and more realistic dataset, the analysis could be extended into:

* interactive Power BI dashboards
* sales KPIs
* product/category comparisons
* customer-level analysis
* profit and margin analysis
* advanced time-series analysis
* anomaly detection
* automated reporting
* SQL-based analysis
* predictive sales models

The current project focuses on the **EDA layer** that would come before many of those steps.

---

## 🌱 Project Takeaway

A spreadsheet of transactions doesn't look particularly interesting.

Start grouping it.

Plot it.

Compare it.

Question it.

Suddenly, patterns begin to appear.

This project was my hands-on practice with that process — using **Python and visualization to turn raw retail records into something that can actually be interpreted.**

---

<p align="center">
  <b>Python · Pandas · Matplotlib · Seaborn · Exploratory Data Analysis</b>
</p>
