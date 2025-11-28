# Renewable Energy Consumption Analysis

A comprehensive Exploratory Data Analysis (EDA) project examining household-level renewable energy adoption patterns, usage trends, and subsidy coverage across different demographics using Python and the Pandas library.

## 📊 Project Overview

This project analyzes a synthetic dataset of household renewable energy usage to uncover key patterns and relationships in renewable energy adoption. The analysis focuses on answering critical questions about energy sources, consumption patterns, household characteristics, and the effectiveness of government subsidy programs.

## 🎯 Key Objectives

The analysis aims to answer five fundamental questions:

1. **What renewable energy sources are most widely adopted?**
2. **Which countries have the highest energy consumption?**
3. **How does household size affect monthly energy usage?**
4. **What is the subsidy coverage for low-income households (rural vs. urban)?**
5. **What are the annual trends in overall renewable energy usage?**

## 📁 Dataset Information

- **Source**: Kaggle (Synthetic Dataset)
- **File**: `Renewable_Energy_Usage_Sampled.csv`
- **Size**: 1,000 household records
- **Time Period**: 2020-2024

### Dataset Features

| Column | Description |
|--------|-------------|
| `Household_ID` | Unique identifier for each household |
| `Country` | Country of residence |
| `Energy_Source` | Type of renewable energy (Solar, Wind, Hydro, Geothermal) |
| `Monthly_Usage_kWh` | Monthly energy consumption in kilowatt-hours |
| `Year` | Year of record |
| `Household_Size` | Number of people in household |
| `Income_Level` | Income classification (Low, Medium, High) |
| `Urban_Rural` | Location type |
| `Adoption_Year` | Year household adopted renewable energy |
| `Subsidy_Received` | Whether household received government subsidy (Yes/No) |
| `Cost_Savings_USD` | Estimated cost savings in USD |

## 🛠️ Technologies Used

- **Python 3.13.9**
- **Pandas**: Data manipulation and analysis
- **NumPy**: Numerical computations
- **Matplotlib**: Data visualization
- **Seaborn**: Statistical data visualization

## 📋 Prerequisites
```bash
# Python 3.13.9 or higher
python --version

# Required packages
conda install pandas numpy matplotlib seaborn
```

## 🚀 Installation & Setup

1. **Clone the repository**
```bash
git clone https://github.com/arjunprakashai1/Energy-Consumption-Analysis.git
cd renewable-energy-analysis
```

2. **Create a virtual environment (recommended)**
```bash
python -m venv energy_consumption
source energy_consumption/bin/activate  # On Windows: energy_consumption\Scripts\activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Dataset placement**
```
project_root/
│
├── Energy Consumption Data/
│   └── Renewable_Energy_Usage_Sampled.csv
│
└── Energy_consumption.ipynb
```

## 📊 Key Findings

### 1. Energy Source Distribution
![Energy sources](/Visuals/Most%20used%20energy%20source.png)
- **Wind energy dominates** with 227 households (highest adoption)
- **Highly balanced adoption** across top three sources: Wind (227), Solar (205), Hydro (199)
- **Geothermal lags** with only 180 households (lowest adoption)

### 2. Top Energy-Consuming Countries
![Top Energy Consuming countries](/Visuals/Countries_usage.png)
- **Colombia** leads with highest median monthly usage (655 kWh)
- **Geographic diversity** in top consumers: Colombia, Egypt, France, UK, Brazil
- **Brazil** ranks in top 5 but significantly below leaders

### 3. Household Size vs. Consumption
![Household size correlation](/Visuals/Household_size.png)
- **No linear correlation** between household size and energy consumption
- **High variability** across all household sizes
- **Single-person households** surprisingly show among the highest consumption (~855 kWh)
- **Smallest household (size 5)** has lowest consumption (~630 kWh)

### 4. Subsidy Coverage Analysis
![Subsidy Coverage](/Visuals/Urban_vs_Rural_subsidies.png)
#### Low-Income Households
- **Urban areas**: 51.9% receive subsidies
- **Rural areas**: 48.7% receive subsidies
- **Coverage gap**: ~50% of low-income households in both areas don't receive subsidies

### 5. Annual Usage Trends (2020-2024)
![Annual Usage Trend](/Visuals/Yearly_usage_trend.png)
- **Overall decline**: -8.47% from 2020 to 2024
- **High volatility**: Range of 15,744 kWh between lowest (2024) and highest (2023) points
- **Sharpest drop**: -9.73% from 2023 to 2024
- **Peak year**: 2023 with 161,850 kWh total usage
- **Lowest year**: 2024 with 146,106 kWh total usage

## 🔍 Analysis Methodology

### Data Cleaning
- Checked for missing values (none found)
- Verified duplicate records (none found)
- Removed unnecessary columns (`Adoption_Year`)
- Validated data types

### Exploratory Analysis Techniques
1. **Univariate Analysis**: Distribution of individual variables
2. **Bivariate Analysis**: Relationships between variables
3. **Grouping & Aggregation**: Category-wise summaries
4. **Trend Analysis**: Time-series patterns

### Visualization Techniques
- **Bar Charts**: Energy source distribution, country comparisons
- **Scatter Plots**: Household size vs. consumption
- **Pie Charts**: Subsidy coverage breakdown
- **Line Charts**: Annual trend analysis

## 📈 Usage

### Running the Jupyter Notebook
```bash
jupyter notebook Energy_consumption.ipynb
```

### Key Code Snippets

**Loading Data:**
```python
import pandas as pd
df = pd.read_csv('../Energy Consumption Data/Renewable_Energy_Usage_Sampled.csv')
```

**Analyzing Energy Sources:**
```python
df_energy_source = df['Energy_Source'].value_counts().reset_index(name='Total_households')
```

**Subsidy Analysis:**
```python
df_rural = df[(df['Income_Level'] == 'Low') & (df['Urban_Rural'] == 'Rural')]
df_urban = df[(df['Income_Level'] == 'Low') & (df['Urban_Rural'] == 'Urban')]
```

## 📌 Project Structure
```
renewable-energy-analysis/
│
├── Energy Consumption Data/
│   └── Renewable_Energy_Usage_Sampled.csv
│
├── Energy_consumption.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```


## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## ⚠️ Disclaimer

This analysis uses a **synthetic dataset** from Kaggle created for educational and analytical purposes. The findings should not be used as a basis for real-world policy decisions or investment choices.

## 👤 Author

**Your Name**
- GitHub: [@arjunprakashai1](https://github.com/arjunprakashai1)
- LinkedIn: [arjun-prakash-ai](https://www.linkedin.com/in/arjun-prakash-ai/)

## 🙏 Acknowledgments

- Dataset source: Kaggle
- Inspiration: Growing interest in renewable energy adoption and sustainability
- Tools: Python data science ecosystem (Pandas, NumPy, Matplotlib, Seaborn)

## 📧 Contact

For questions or feedback, please open an issue or contact [arjunprakash.ai1@gmail.com](mailto:arjunprakash.ai1@gmail.com)

---

**Note**: This project is part of a data analysis portfolio demonstrating skills in:
- Data cleaning and preprocessing
- Exploratory Data Analysis (EDA)
- Data visualization
- Statistical analysis
- Python programming
- Jupyter Notebooks