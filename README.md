# Consumer-Complaint-Trends-and-Company-Response-Analysis: Bank of America (2017–2023)

## Project Overview

This project investigates consumer complaint patterns and company response trends using a dataset of **62,516 consumer complaints** submitted to the Consumer Financial Protection Bureau (CFPB) between May 2017 and August 2023.

The analysis explores how complaint volumes change over time, which financial products and issues generate the most complaints, how companies respond to consumers, and how long complaints take to be forwarded from the CFPB to the company.

The project applies Exploratory Data Analysis (EDA), data cleaning, visualization, and statistical hypothesis testing to identify patterns and generate insights relevant to consumer protection and financial services.

## Research Objectives

The main objectives are to:

- Examine annual and monthly complaint submission trends.
- Identify the financial products and issues associated with the highest complaint volumes.
- Investigate the distribution of company responses to consumers.
- Analyse CFPB complaint-forwarding intervals.
- Test whether response patterns and forwarding intervals differ across product categories and reporting years.
- Translate the findings into practical recommendations for financial institutions.

## Research Questions and Hypotheses

The analysis addresses four research questions:

**RQ1: Do CFPB complaint-forwarding intervals differ across financial product categories?**

- H₀: Forwarding intervals do not differ significantly across product categories.
- H₁: At least one product category has a different forwarding-interval distribution.

**RQ2: Is there an association between financial product category and company response type?**

- H₀: Product category and company response type are independent.
- H₁: Product category and company response type are associated.

**RQ3: Is there an association between reporting year and whether a company responded on time?**

- H₀: Reporting year and timely response status are independent.
- H₁: Reporting year and timely response status are associated.

**RQ4: Is there a relationship between time and monthly complaint volume?**

- H₀: There is no monotonic relationship between reporting month and monthly complaint volume.
- H₁: There is a monotonic relationship between reporting month and monthly complaint volume.

## Dataset Description

The dataset contains 62,516 complaint records and 12 variables, including:

| Variable | Description |
|---|---|
| Complaint ID | Unique complaint identifier |
| Submitted via | Channel through which the complaint was submitted |
| Date submitted | Date the CFPB received the complaint |
| Date received | Date the complaint was forwarded to the company |
| State | Consumer's state |
| Product | Financial product category |
| Sub-product | More specific product classification |
| Issue | Main complaint issue |
| Sub-issue | More specific complaint classification |
| Company public response | Public response information |
| Company response to consumer | Recorded company response category |
| Timely response? | Whether the company responded within the required timeframe |

The project brief identifies the complaints as relating to Bank of America. The supplied dataset extract does not contain a company-name field, so this designation cannot be independently verified from the extract itself.

## Tools and Technologies

- **Python:** Main programming language
- **Pandas and NumPy:** Data manipulation and numerical analysis
- **Matplotlib and Seaborn:** Data visualization
- **SciPy:** Statistical hypothesis testing
- **Jupyter Notebook:** Reproducible analysis and documentation

## Methodology

The project follows these stages:

1. **Data loading and inspection:** Importing the dataset and reviewing its structure, dimensions, data types and completeness.
2. **Data quality assessment:** Checking missing values, duplicate records, unique complaint IDs and date validity.
3. **Data cleaning and preparation:** Converting date columns, deriving reporting periods and calculating CFPB forwarding intervals.
4. **Exploratory data analysis:** Examining complaint distributions by year, month, product, issue and response category.
5. **Statistical analysis:** Applying non-parametric and categorical statistical tests to investigate the research hypotheses.
6. **Interpretation:** Translating the statistical and descriptive findings into practical financial-services insights.

### Statistical Techniques

- **Kruskal-Wallis H-test:** Compares forwarding-interval distributions across product categories.
- **Chi-square test of independence:** Examines associations between product category and company response type, and between reporting year and timely response status.
- **Spearman rank correlation:** Evaluates the monotonic relationship between time and monthly complaint volume.
- **Cramér's V and epsilon-squared:** Used to assess the magnitude of selected statistical associations.

## Key Findings

The analysis produced the following descriptive and statistical findings:

### Complaint Trends

- The dataset contains 62,516 complaints.
- Annual complaint volumes increased from 5,394 in 2017 to 12,953 in 2022.
- Checking and savings accounts recorded the highest complaint volume, with 24,814 complaints.
- Managing an account was the most frequently recorded issue, accounting for 15,109 complaints (approximately 24.17%).

### Company Responses

- 41,044 complaints (approximately 65.65%) were recorded as closed with explanation.
- 14,697 were closed with monetary relief.
- 5,273 were closed with non-monetary relief.
- Among records with a known timely-response status, approximately 96.06% were marked as timely.

### CFPB Forwarding Intervals

- The median forwarding interval was zero days.
- The mean forwarding interval was approximately 1.22 days.
- 49,634 complaints (approximately 79.39%) were forwarded on the same day.
- The maximum recorded interval was 275 days.

**Important distinction:** The forwarding interval measures the time between the CFPB receiving a complaint and forwarding it to the company. It does not measure the company's investigation, response or resolution time.

### Statistical Test Results

| Research question | Statistical method | Result |
|---|---|---|
| RQ1 | Kruskal-Wallis H-test | H = 1527.39, p < 0.001 |
| RQ2 | Chi-square test | χ² = 5549.33, p < 0.001 |
| RQ3 | Chi-square test | χ² = 2662.50, p < 0.001 |
| RQ4 | Spearman correlation | ρ = 0.7784, p < 0.001 |

The tests indicate statistically significant differences or associations in the analysed data. Statistical significance does not necessarily imply a large practical effect or establish causation.

## Business and Financial Services Implications

The findings highlight several areas that financial institutions can investigate further:

- **Account management:** The high volume of account-management complaints supports reviewing account servicing processes, communication and customer support.
- **Product-specific monitoring:** Differences in complaint and response patterns across products can help institutions identify areas requiring closer monitoring.
- **Response management:** Timely response performance should be monitored alongside complaint outcomes and customer experience.
- **Operational efficiency:** Forwarding delays can be examined to identify potential inefficiencies in complaint intake and routing.
- **Data-driven decision-making:** Complaint data can support service-quality monitoring, operational risk assessment and resource allocation.

## Limitations

- The dataset is observational and does not establish causal relationships.
- Complaint volumes do not independently prove misconduct or the prevalence of problems among all customers.
- The supplied extract does not contain a company-name field; the Bank of America designation comes from the project brief.
- The dataset begins in May 2017 and ends in August 2023, making 2017 and 2023 partial reporting years.
- Missing values in some fields, particularly sub-issue and timely response status, may affect interpretation.
- Blank timely-response values are not automatically classified as negative responses; some are associated with complaints still in progress.
- The CFPB forwarding interval should not be interpreted as company resolution time.
- Monthly complaint counts may be affected by seasonality, reporting behaviour and time-series autocorrelation.

## Repository Structure

```text
consumer-complaint-analysis/
│
├── Week4_Consumer_Complaint_Analysis.ipynb
├── Consumer_Complaints.xlsx - Data.csv
├── ConsumerComplaints_DataDictionary.csv
├── README.md
└── .gitignore
```

## How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/CharityNduati/Consumer-Complaint-Trends-and-Company-Response-Analysis
cd consumer-complaint-analysis
```

### 2. Install the required libraries

```bash
pip install pandas numpy matplotlib seaborn scipy openpyxl jupyter
```

### 3. Launch Jupyter Notebook

```bash
jupyter notebook
```

### 4. Run the analysis

Open `Week4_Consumer_Complaint_Analysis.ipynb` and execute the notebook cells in sequence.

Ensure that both CSV source files are available in the project directory or in the location configured in the notebook.

## Conclusion

This project demonstrates how consumer complaint data can be analysed to identify trends, understand product-specific complaint patterns, evaluate response categories and investigate operational differences.

By combining exploratory analysis with statistical testing, the project provides a reproducible foundation for evidence-based decision-making in financial services.

---

**Project:** Week 4 – Consumer Complaint Patterns and Response Trends  
**Dataset:** CFPB consumer complaint extract, 2017–2023  
**Tools:** Python, Pandas, NumPy, Matplotlib, Seaborn, SciPy and Jupyter Notebook