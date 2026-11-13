# UK Workforce Planning and Labour Market Analysis

A data analytics project combining Python, SQL, and Power BI to analyze workforce trends, pay competitiveness, and succession risks against official UK labour market data.

## About The Project

When organizations plan their hiring and retention strategies, they often look only at their internal numbers. However, without comparing internal data to the broader labour market, it is hard to tell whether pay is fair, where hiring bottlenecks might happen, or which departments are vulnerable when experienced staff retire.

I built this project to practice full-cycle data analytics on a realistic business problem. The goal is to bring together public labour market statistics from the UK Office for National Statistics (ONS) and job vacancy data, and compare them against an organizational workforce roster.

Through this project, I wanted to answer three practical questions:
1. How do internal company salaries compare to regional market medians across different job roles?
2. Which departments face the highest skills shortages based on real market demand?
3. Which critical positions have imminent retirement risks without an identified successor in place?

## How The Project Works

The analysis follows four clear steps from raw data collection to reporting:

1. Data Collection and Generation
   The project uses public UK economic data, including ONS Annual Survey of Hours and Earnings (ASHE) salary tables and vacancy statistics. Because real company HR records are private, I created a calibrated synthetic dataset of 800 employee records that reflects realistic department structures, salaries, age profiles, and job titles.

2. Data Cleaning and Pipeline (Python)
   A set of Python scripts standardizes job titles using Standard Occupational Classification (SOC) codes, calculates wage gaps, flags succession vulnerabilities, and prepares clean tables for analysis.

3. Database Storage and SQL Queries (SQLite)
   The cleaned data is loaded into a SQLite database. I wrote dedicated SQL queries to compute salary differences, evaluate skills shortages, and score succession risks across departments.

4. Interactive Reporting (Power BI and Excel)
   The final results are presented in a Power BI dashboard and summary reports, giving decision makers an intuitive way to filter by department, region, and job level.

## Key Findings From The Analysis

- Salary Alignment: In high-demand roles such as software engineering and data analytics, internal mid-level salaries lagged behind regional market medians by 8% to 14%, pointing to potential turnover risks.
- Succession Bottlenecks: Approximately 18% of critical technical roles had team members approaching retirement within five years with no designated backup or junior apprentice in training.
- Regional Differences: Pay disparities were most pronounced in London and the South East, while regional operations showed closer parity to published ONS benchmarks.

## Technologies Used

- Python (pandas, numpy, sqlite3, requests, pytest): Used for data processing, synthetic HR data generation, statistical calculations, and automated testing.
- SQL (SQLite): Used for relational data modeling, joins, aggregations, window functions, and business metric calculations.
- Power BI: Used for building interactive reports, data modeling, and designing visual dashboards for non-technical stakeholders.
- Excel and CSV: Used for data exports, quick tabular lookups, and reviewing intermediate calculations.

## Repository Structure

- data/: Contains raw benchmark datasets and processed tables used in the pipeline.
- scripts/: Python scripts for data generation, Nomis and Adzuna API fetching, and pipeline execution.
- queries/: SQL scripts for running salary gap, skills shortage, and succession risk queries.
- powerbi/: Power BI report files and dashboard preview images.
- reports/: Analytical summaries, case studies, and documentation.
- tests/: Pytest suite to verify data schemas, completeness, and calculation logic.
- run_pipeline.py: The main script that runs the entire workflow from start to finish.

## How To Run This Project Locally

### 1. Clone the repository
```bash
git clone https://github.com/sharmi2112-hub/uk-workforce-planning-analysis.git
cd uk-workforce-planning-analysis
```

### 2. Set up a Python virtual environment
```bash
python -m venv venv
```

On Windows:
```bash
venv\Scripts\activate
```

On macOS or Linux:
```bash
source venv/bin/activate
```

### 3. Install required packages
```bash
pip install -r requirements.txt pytest
```

### 4. Run the data pipeline
```bash
python run_pipeline.py
```

This script cleans the data, runs the necessary transformations, and generates the SQLite database.

### 5. Run the tests
```bash
pytest
```

This validates that all data files are correctly structured and all calculations pass sanity checks.

### 6. Explore the SQL queries and Dashboard
- Open the .sql files in the queries/ directory using any SQLite client (such as DB Browser for SQLite) to inspect the queries.
- Open the .pbix file in the powerbi/ directory with Power BI Desktop to view the interactive visualizations.

## What I Learned From Building This

Building this project helped me connect several important data analyst skills:
- How to work with macroeconomic data from public agencies like the ONS.
- How to structure end-to-end data pipelines in Python that are repeatable and testable.
- How to write clean, multi-table SQL queries that solve concrete business problems rather than just textbook exercises.
- How to translate technical findings into clear, accessible recommendations that anyone can understand.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
