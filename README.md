# Employee Data Analysis Pipeline 

## Project Overview
This project provides a comprehensive end-to-end data analysis of an employee dataset. The primary goal is to extract actionable insights regarding salary distributions, employee demographics, and attrition trends using Python. 

The analysis strictly follows a logical data pipeline: from initial loading and exploratory data analysis (EDA), through deep data cleaning and feature engineering, culminating in statistical aggregations and data visualization.

## Tech Stack
* **Language:** Python
* **Data Manipulation & Analysis:** Pandas, NumPy
* **Data Visualization:** Matplotlib, Seaborn
* **Environment:** Jupyter Notebook

## Methodology & Data Flow

### 1. Data Exploration & Loading
* Loaded the raw Excel dataset into a Pandas DataFrame.
* Conducted structural inspection (dtypes, shape, null counts).
* Computed descriptive statistics and identified salary outliers using NumPy arrays and standard deviation thresholds.

### 2. Data Cleaning & Preprocessing
* Standardized textual data (trimming whitespace, title casing).
* Handled missing values logically (e.g., assigning "Not Disclosed" to sparse categorical fields and utilizing medians for numericals).
* Resolved ID duplications by generating unique sequential identifiers (e.g., `_2`).
* Converted temporal data into proper `datetime` formats.

### 3. Feature Engineering
* Calculated employee tenure (`Tenure_Years`) based on hire and exit dates.
* Extracted specific datetime features (Hire Year, Quarter, Day of Week) to analyze seasonal hiring trends.
* Created a dynamic `Status` column (Active/Terminated).

### 4. Statistical Aggregation & Grouping
* Utilized `pd.NamedAgg` for clean, explicit aggregations.
* Built Crosstabs to analyze headcount by department and ethnicity.
* Generated Pivot Tables to compute average salaries by department and gender, successfully deriving the **Pay Gap Percentage**.
* Applied `.transform()` to calculate individual salary deviations from departmental averages.

### 5. Data Visualization
* **Matplotlib:** Bar charts for average salaries, histograms for age distribution, and line charts tracking hiring and attrition trends over time.
* **Seaborn:** Boxplots to spot salary outliers per department.

## Repository Structure
* `Employee_Data_Analysis.ipynb`: The main Jupyter Notebook containing all the executed Python code, logical steps, and inline documentation.
* `Employee Sample Data - A.xlsx`: The raw input dataset.
* `Cleaned_Employee_Data_Analysis.xlsx`: The final output workbook containing the cleaned data and all summary tables, organized into separate sheets.
* `/Charts_Output/`: A directory containing all the exported high-resolution PNG charts.
* `requirements.txt`: List of dependencies required to run the project.

## How to Run
1. Clone this repository.
2. Install the required libraries using: `pip install -r requirements.txt`
3. Open `Employee_Data_Analysis.ipynb` in Jupyter Notebook and run the cells sequentially.
