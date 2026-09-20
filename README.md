Dr. Semmelweis and the Effect of Handwashing: A Data Analysis Story

Python Jupyter License Data Science

A historical medical dataset analysis demonstrating the life-saving impact of handwashing. This project uses real 19th-century medical records to uncover one of history's greatest medical breakthroughs.

📖 Project Overview

This project analyzes the groundbreaking work of Dr. Ignaz Semmelweis, a Hungarian physician who discovered that handwashing drastically reduced maternal mortality in childbirth during the 1840s. Using historical data from two maternity clinics in Vienna, this analysis demonstrates how a simple hygiene practice saved thousands of lives.

Time Period: 1841-1847
Location: Vienna General Hospital (Clinic 1 & 2)
Key Finding: Handwashing reduced maternal mortality from ~10% to ~2% (approximately 80% reduction)

📊 Dataset Description
Data Sources
yearly_deaths_by_clinic.csv - Annual death statistics (1841-1846)
monthly_deaths.csv - Monthly death records (1841-1847+)
Features
Column	Type	Description
year	Integer	Year of record (1841-1846)
date	DateTime	Month and year of record
clinic	String	Clinic identifier (clinic 1 or clinic 2)
births	Integer	Number of births in that period
deaths	Integer	Number of maternal deaths (childbed fever)
Proportion of Deaths	Float	Death rate (deaths/births)
Key Statistics
Total Records: 1,599 births in yearly data
Clinic 1: Higher mortality due to medical students involved in autopsies
Clinic 2: Lower mortality - staffed primarily by experienced midwives
Analysis Period: 6+ years of before/after data
🔬 Historical Context
The Problem: Childbed Fever (Puerperal Fever)

In the 1840s, childbed fever was one of the leading causes of maternal death. Doctors had no explanation for why it occurred or how to prevent it. The mortality rates were alarmingly high:

Clinic 1: 9.9% of mothers died after childbirth
Clinic 2: 3.9% of mothers died after childbirth
Semmelweis's Hypothesis

Dr. Semmelweis observed that:

Many medical students worked in Clinic 1
These students performed autopsies before assisting in deliveries
They did NOT wash their hands between activities
"Cadaverous particles" were likely transferred to pregnant women
The Solution

In June 1847, Dr. Semmelweis made handwashing mandatory for all medical staff. The results were remarkable:

Before Handwashing: ~10% mortality rate
After Handwashing: ~2% mortality rate
Lives Saved: Hundreds of mothers' lives in just one hospital
📈 Project Analysis Sections
Section 1: Yearly Data Analysis
Goal: Compare mortality patterns between the two clinics from 1841-1846
Visualizations:
Bar charts showing annual death counts
Line plots comparing proportion of deaths over time
Yearly mortality trends by clinic
Key Finding: Clinic 1 consistently had 2.5x higher mortality rates
Section 2: Monthly Data Analysis
Goal: Track mortality changes before and after handwashing implementation
Time Split: June 1, 1847 marks the beginning of mandatory handwashing
Visualizations:
Before handwashing trend (Jan 1841 - May 1847)
After handwashing trend (Jun 1847 onwards)
Combined comparison showing dramatic improvement
Key Finding: Immediate and sustained reduction in mortality
Section 3: Detailed Questions & Answers (10 Q&A Sections)

Deep-dive analysis answering critical questions:

Average deaths comparison - Clinic-by-clinic statistics
Total impact - Cumulative births and deaths across the period
Extreme values - Highest and lowest mortality months
Root cause analysis - Why Clinic 1 had higher rates
Handwashing impact - Percentage reduction in mortality (80%!)
Lives saved - Quantifying the human impact
Month-by-month trends - Immediate effectiveness verification
Baseline mortality - Pre-handwashing era context
Turning point - Most dramatic improvement month
Statistical consistency - Coefficient of variation analysis
🛠️ Technologies & Libraries Used
python
# Core Libraries
pandas      # Data manipulation and analysis
numpy       # Numerical computing
matplotlib  # Data visualization
seaborn     # Statistical data visualization (optional)

# Tools
Jupyter Notebook  # Interactive computing environment
Python 3.7+      # Programming language
Installation
bash
# Clone the repository
git clone https://github.com/yourusername/semmelweis-analysis.git
cd semmelweis-analysis

# Install dependencies
pip install pandas numpy matplotlib jupyter seaborn

# Launch Jupyter Notebook
jupyter notebook Dr__Semmelweis_updated.ipynb
📊 Key Visualizations
1. Yearly Mortality Comparison

Bar charts showing annual deaths in each clinic, revealing Clinic 1's consistently higher death toll.

2. Proportion of Deaths Over Time

Line plots displaying the mortality rate trends, showing the stark difference between the two clinics.

3. Before vs. After Handwashing

Side-by-side time series graphs demonstrating the immediate impact of implementing handwashing protocols.

4. Combined Trend Analysis

Overlay comparison showing the dramatic drop in mortality when handwashing became mandatory.

🔍 Main Findings
Finding 1: Clinic Mortality Disparity
Clinic 1 Average Mortality: 10.45%
Clinic 2 Average Mortality:  3.86%
Difference:                  6.59 percentage points
Impact: Clinic 1 had 2.7x higher mortality rate
Finding 2: Handwashing Impact
Before Handwashing (Pre-June 1847):
  - Mortality Rate: ~10.45%
  - Monthly Average Deaths: 36.3

After Handwashing (Jun 1847+):
  - Mortality Rate: ~2.10%
  - Monthly Average Deaths: 6.7
  
Reduction: 80% decrease in maternal mortality
Finding 3: Immediate Effectiveness

The mortality rate dropped sharply in the first month after implementation and remained consistently low, proving handwashing was immediately effective and sustainable.

Finding 4: Lives Saved

Based on the post-handwashing implementation period, approximately 300+ lives were saved simply by requiring doctors to wash their hands.

📝 Code Examples
Basic Data Loading & Exploration
python
import pandas as pd
import numpy as np

# Load yearly data
yearly_df = pd.read_csv("yearly_deaths_by_clinic.csv")
print(yearly_df.shape)  # (6, 4)
print(yearly_df.info())

# Calculate mortality proportion
yearly_df["Proportion of Deaths"] = yearly_df["deaths"] / yearly_df["births"]

# Group by clinic
clinic_1 = yearly_df[yearly_df["clinic"] == "clinic 1"]
clinic_2 = yearly_df[yearly_df["clinic"] == "clinic 2"]
Visualization Example
python
import matplotlib.pyplot as plt

# Plot mortality trends
fig, ax = plt.subplots(figsize=(10, 6))
ax = clinic_1.plot(x="year", y="Proportion of Deaths", label="Clinic 1", color="red")
clinic_2.plot(x="year", y="Proportion of Deaths", label="Clinic 2", ax=ax, color="green")

plt.title("Clinic Comparison: Proportion of Deaths by Year")
plt.xlabel("Year")
plt.ylabel("Proportion of Deaths")
plt.legend()
plt.show()
Statistical Analysis
python
# Compare before and after handwashing
before_washing = monthly_df[monthly_df["date"] < pd.to_datetime('1847-06-01')]
after_washing = monthly_df[monthly_df["date"] >= pd.to_datetime('1847-06-01')]

before_mean = before_washing["Proportion of Deaths"].mean()
after_mean = after_washing["Proportion of Deaths"].mean()

reduction = ((before_mean - after_mean) / before_mean) * 100
print(f"Handwashing reduced mortality by {reduction:.1f}%")
💡 Skills Demonstrated

✅ Data Cleaning & Preprocessing
✅ Exploratory Data Analysis (EDA)
✅ Statistical Analysis & Interpretation
✅ Data Visualization (Matplotlib, Seaborn)
✅ Time Series Analysis
✅ Historical Data Analysis
✅ Python Programming (Pandas, NumPy)
✅ Jupyter Notebook Development
✅ Report Generation & Documentation
✅ Problem Solving & Critical Thinking

📚 Educational Value

This project is ideal for:

Data Science Students: Learning EDA and statistical analysis
Medical Professionals: Understanding the history of hygiene protocols
History Enthusiasts: Exploring how data revealed a life-saving practice
Academic Projects: Using historical medical records for analysis
Portfolio Building: Demonstrating real-world data analysis skills
🎯 Key Takeaways
Data Tells a Story: Historical data revealed patterns doctors couldn't see
Simple Solutions Work: Handwashing was free and effective
Evidence-Based Medicine: Using data to support medical decisions
Lives Matter: This discovery saved hundreds of lives
Science Prevails: Eventually, Semmelweis's findings were accepted universally
Modern Relevance

Dr. Semmelweis's discovery remains relevant today:

COVID-19 Pandemic: Handwashing crucial for virus prevention
Hospital-Acquired Infections: Hand hygiene protocols save lives daily
Public Health: Simple hygiene practices prevent disease spread
Data-Driven Decisions: Using evidence to make medical policies
📋 Project Structure
├── Dr__Semmelweis_updated.ipynb
│   ├── Section 1: Import & Load Data
│   ├── Section 2: Yearly Data Analysis
│   ├── Section 3: Clinic Comparison
│   ├── Section 4: Monthly Data Analysis
│   ├── Section 5: Before vs. After Analysis
│   └── Section 6: 10 Detailed Q&A Sections
│
├── yearly_deaths_by_clinic.csv
├── monthly_deaths.csv
└── README.md
🔗 Data Sources
Historical Records: Vienna General Hospital Archives (1841-1847)
Dataset Format: CSV (Comma-Separated Values)
Encoding: UTF-8 (Latin-1 compatible)
📞 Contact & Author

Developed by: Data Science Enthusiast
Education: MCA (Master of Computer Applications) - GLS University
Email: harshsevkani5t@gmail.com
Phone: +91 9998793930

📄 License

This project is open-source and available under the MIT License. Feel free to use, modify, and share for educational purposes.

🌟 Acknowledgments
Dr. Ignaz Semmelweis - For his groundbreaking discovery and dedication to maternal health
Vienna General Hospital - For preserving historical medical records
Data Science Community - For tools and libraries that make analysis possible
🚀 Future Enhancements

Potential extensions to this analysis:

 Interactive visualizations using Plotly
 Statistical hypothesis testing
 Machine learning models to predict mortality
 Comparative analysis with other hospitals
 Geographic and temporal analysis
 Dashboard creation with Tableau/Power BI
