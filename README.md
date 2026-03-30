<div align='center'>
  <img src="https://media.tenor.com/NWjt1i9eFE4AAAAM/duck.gif">
  
</div>
<br>

# 📊 Cohort Customer Analysis

> Analyzing customer retention rates from historical sales data and visualizing insights with Python libs.

---

## 🧭 Overview

This project performs a **cohort analysis** on historical sales data to understand how customer retention evolves over time. By grouping customers into cohorts based on their first purchase date, we track their behavior across subsequent periods — revealing trends in loyalty, churn, and lifetime value.

The findings are transformed into clear, interactive, and publication-ready visualizations using a suite of Python libraries.

---

## 🎯 Objectives

- Extract and clean historical sales data for cohort segmentation
- Define cohorts based on customers' first transaction date (monthly/quarterly)
- Calculate **retention rates** across cohort periods
- Identify patterns in customer churn and long-term engagement
- Visualize insights using multiple Python visualization libraries

---

## 🗂️ Project Structure

```
cohort-analysis/
│
├── data/
│   ├── raw/                    # Raw, unprocessed sales data
│   └── processed/              # Cleaned and transformed datasets
│
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_cohort_construction.ipynb
│   ├── 03_retention_analysis.ipynb
│   └── 04_visualization.ipynb
│
├── src/
│   ├── data_loader.py          # Data ingestion and preprocessing
│   ├── cohort_builder.py       # Cohort grouping and pivot logic
│   ├── retention.py            # Retention rate calculations
│   └── visualizer.py           # Plotting functions and chart exports
│
├── outputs/
│   ├── figures/                # Exported charts and plots
│   └── reports/                # Summary reports
│
├── requirements.txt
├── .gitignore
└── README.md
```

---

## 🔬 Methodology

### 1. Data Preparation
- Load raw transaction records (order ID, customer ID, purchase date, revenue)
- Handle missing values, duplicates, and date parsing
- Filter to a relevant time window

### 2. Cohort Construction
- Assign each customer to a **cohort** based on their **first purchase month**
- Compute the **cohort index** (number of months since first purchase) for each transaction

### 3. Retention Rate Calculation
- Build a cohort pivot table: rows = cohort month, columns = cohort index
- Divide each cell by the cohort's initial customer count to get **retention %**

### 4. Visualization & Insights
- Heatmaps, line charts, bar charts, and interactive dashboards to surface key findings

---

## 📈 Visualizations

This project uses multiple Python libraries depending on the use case:

| Library | Use Case |
|---|---|
| **Matplotlib** | Static charts, subplots, publication-ready figures |
| **Seaborn** | Heatmaps, statistical plots, cohort retention grids |
| **Plotly** | Interactive charts, hover tooltips, time-series analysis |
| **Bokeh** | Web-embeddable dashboards, linked interactive plots |

### Key Charts Produced
- 🟥 **Retention Heatmap** — cohort × period grid colored by retention %
- 📉 **Retention Curve** — drop-off trends per cohort over time
- 📊 **Cohort Size Bar Chart** — volume of customers acquired per cohort
- 🔁 **Average Retention Line** — benchmark across all cohorts
- 🌐 **Interactive Dashboard** — filterable cohort explorer (Plotly / Bokeh)

---

## ⚙️ Installation

### Prerequisites
- Python 3.8+
- pip or conda

### Setup

```bash
# Clone the repository
git clone https://github.com/your-username/cohort-analysis.git
cd cohort-analysis

# Create and activate a virtual environment
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### Dependencies (`requirements.txt`)

```
pandas>=2.0.0
numpy>=1.24.0
matplotlib>=3.7.0
seaborn>=0.12.0
plotly>=5.15.0
bokeh>=3.2.0
jupyterlab>=4.0.0
openpyxl>=3.1.0
```

---

## 🚀 Usage

### Run via Jupyter Notebooks

```bash
jupyter lab
```

Open and execute notebooks in order (`01` → `04`) inside the `notebooks/` folder.

### Run via Script

```bash
# Full pipeline: load → build cohorts → calculate retention → export charts
python src/main.py --input data/raw/sales.csv --output outputs/figures/
```

---

## 📋 Data Format

The pipeline expects a CSV file with at minimum the following columns:

| Column | Type | Description |
|---|---|---|
| `order_id` | string | Unique transaction identifier |
| `customer_id` | string | Unique customer identifier |
| `order_date` | date | Date of the transaction |
| `revenue` | float | Transaction value (optional) |

---

## 📊 Sample Output

```
Cohort Retention Table (%)

Cohort      Month 0   Month 1   Month 2   Month 3   Month 4
─────────────────────────────────────────────────────────────
2023-01     100.0%    42.3%     28.7%     21.4%     17.2%
2023-02     100.0%    38.9%     25.1%     19.8%     15.6%
2023-03     100.0%    45.1%     31.2%     24.0%     19.3%
2023-04     100.0%    40.7%     27.9%     —         —
2023-05     100.0%    44.2%     —         —         —
```

---

## 🔍 Key Insights (Example)

- **Month 1 drop-off** is consistently the steepest, averaging ~58% churn after the first purchase
- Cohorts acquired in **Q1** tend to show stronger long-term retention than Q3/Q4 cohorts
- A retention rate above **20% at Month 3** is a strong indicator of high-LTV customers

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-analysis`)
3. Commit your changes (`git commit -m 'Add new cohort segmentation logic'`)
4. Push to the branch (`git push origin feature/new-analysis`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 👤 Author

**Your Name**
- GitHub: [@VoPhuongAnh](https://github.com/VoPhuongAnh)
- LinkedIn: [Irenee Wu](linkedin.com/in/ireneewu)

---

*Built with 🐍 Python and a passion for data-driven decision making.*
