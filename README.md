# Life Expectancy Analysis (WHO Dataset)

## Table of Contents

- [Project Overview](#project-overview)
- [Team Information](#team-information)
- [Dataset](#dataset)
- [Research Questions](#research-questions)
- [Key Findings](#key-findings)
- [Project Structure](#project-structure)
- [Installation & Setup](#installation--setup)
- [Dependencies](#dependencies)
- [How to Run](#how-to-run)
- [License](#license)

---

## Project Overview

This project analyzes the **Life Expectancy dataset** from the World Health Organization (WHO), covering health data from **179 countries** worldwide between **2000-2015**. 

The analysis focuses on understanding:
- How economic factors (GDP) influence life expectancy
- The role of education (schooling) in population health
- Impact of vaccination programs on mortality rates
- Differences between developed and developing nations
- Building predictive models using machine learning

### Objectives:
1. **Exploratory Data Analysis**: Understand data distributions, correlations, and patterns
2. **Hypothesis Testing**: Validate public health theories (e.g., Preston Curve)
3. **Machine Learning**: Build accurate life expectancy prediction models
4. **Policy Insights**: Provide actionable recommendations for health policymakers

---

## Team Information

| Name | Student ID |
|------|------------|
| Cao Trần Bá Đạt | 23127168 |
| Trần Hoài Thiện Nhân | 23127238 |
| Bùi Nam Việt | 23127516 |

---

## Dataset

### Source
- **Platform**: Kaggle
- **Dataset**: [Life Expectancy (WHO) - Updated](https://www.kaggle.com/datasets/lashagoch/life-expectancy-who-updated)
- **Original Author**: Lasha Gochiashvili (corrected version of KumarRajarshi's dataset)
- **Publication Date**: 2023
- **License**: [CC0 1.0 Universal (Public Domain)](https://creativecommons.org/publicdomain/zero/1.0/)

### Description
| Attribute | Value |
|-----------|-------|
| **Rows** | 2,864 |
| **Columns** | 21 |
| **Time Period** | 2000 - 2015 |
| **Countries** | 179 |
| **Target Variable** | Life_expectancy |

### Features
The dataset includes:
- **Health Indicators**: Adult mortality, Infant deaths, Under-five deaths, HIV incidents, BMI, Thinness rates
- **Vaccination Coverage**: Hepatitis B, Polio, Diphtheria, Measles
- **Economic Factors**: GDP per capita, Economy status (Developed/Developing)
- **Social Factors**: Schooling (years), Population
- **Lifestyle Factors**: Alcohol consumption

---

## Research Questions

The project investigates **7 meaningful questions**:

| # | Question | Focus Area |
|---|----------|------------|
| 1 | Why did life expectancy trends 2000–2015 vary across countries and regions? | Regional Analysis |
| 2 | What are the key factors to improve longevity growth? | Factor Analysis |
| 3 | How to assess factor importance and build accurate prediction models? | Machine Learning |
| 4 | Schooling vs. GDP: Which drives life expectancy more? (Preston Curve) | Economic Analysis |
| 5 | What factors help poor countries achieve high life expectancy? | Development Paradox |
| 6 | What factors are needed to reduce infant mortality? | Child Health |
| 7 | How do lifestyle factors (Alcohol, BMI) impact life expectancy? | Paradox of Affluence |

---

## Key Findings

### 1. The Preston Curve Validated
- GDP has **logarithmic relationship** with life expectancy (diminishing returns)
- **Saturation point**: ~$20,000 GDP per capita beyond which additional wealth has minimal impact
- In developing countries, **education has 2x higher impact** than GDP on life expectancy

### 2. Vaccination > Economic Growth for Child Survival
- Correlation: Vaccination vs. Mortality Reduction = **-0.43** (moderate-strong)
- Correlation: GDP Growth vs. Mortality Reduction = **-0.11** (weak)
- Poor countries with >90% vaccination coverage achieve mortality rates comparable to upper-middle-income nations

### 3. Machine Learning Model Performance
- **Random Forest Regressor** achieved excellent predictive accuracy
- Top predictive features: Under-five deaths (73.8%), Adult mortality (22.8%)
- **Stratified sampling by region** crucial for unbiased model evaluation

### 4. The "Low GDP Overachiever" Phenomenon
- Some poor countries achieve life expectancy comparable to rich nations
- Key success factors: High vaccination coverage (88.6% vs 91.1% in rich countries), low alcohol consumption, effective HIV control
- Geographic concentration: Asia and Central America produce most "overachievers"

### 5. Global Health Inequality Patterns
- Extreme right skew in GDP and HIV data reflects real-world disparities
- Africa faces "geographical penalty": tropical diseases, conflict, climate
- Education is a long-term investment; emergency health interventions yield faster returns

---

## Project Structure

```
Life_Expectancy_WHO/
│
├── data/
│   └── Life-Expectancy-Data-Updated.csv    # Raw dataset
│
├── src/
│   └── main.ipynb                           # Main analysis notebook
│
└── README.md                                # This file
```

---

## Installation & Setup

### Prerequisites
- Python 3.8 or higher
- Jupyter Notebook or JupyterLab

### Clone the Repository
```bash
git clone https://github.com/Shinoaki0145/Life_Expectancy_WHO.git
cd Life_Expectancy_WHO
```

### Create Virtual Environment (Recommended)
```bash
python -m venv venv

# Windows
venv\Scripts\activate

# macOS/Linux
source venv/bin/activate
```

### Install Dependencies
```bash
pip install -r requirements.txt
```

Or install manually:
```bash
pip install numpy pandas matplotlib seaborn scikit-learn scipy statsmodels
```

---

## Dependencies

| Package | Version | Purpose |
|---------|---------|---------|
| `numpy` | ≥1.24.0 | Numerical computing |
| `pandas` | ≥2.0.0 | Data manipulation |
| `matplotlib` | ≥3.7.0 | Data visualization |
| `seaborn` | ≥0.12.0 | Statistical visualization |
| `scikit-learn` | ≥1.3.0 | Machine learning models |
| `scipy` | ≥1.10.0 | Statistical functions |
| `statsmodels` | ≥0.14.0 | Statistical modeling (OLS regression) |

### requirements.txt
```
numpy>=1.24.0
pandas>=2.0.0
matplotlib>=3.7.0
seaborn>=0.12.0
scikit-learn>=1.3.0
scipy>=1.10.0
statsmodels>=0.14.0
```

---

## How to Run


1. Open the project folder in VS Code
2. Install the Python and Jupyter extensions
3. Open `src/main.ipynb`
4. Select Python kernel and run all cells

### Execution Order
The notebook is designed to run sequentially:
1. **Section 1-3**: Dataset information and loading
2. **Section 4**: Data exploration and preprocessing
3. **Section 5**: Analysis of 7 research questions
4. **Section 6**: Project summary and reflections

---

## License

This project uses the [Life Expectancy WHO Dataset](https://www.kaggle.com/datasets/lashagoch/life-expectancy-who-updated) which is released under [CC0 1.0 Universal (Public Domain Dedication)](https://creativecommons.org/publicdomain/zero/1.0/).

You are free to:
- Copy, modify, distribute, and perform the work
- Use for commercial purposes
- All without asking permission

---

## Acknowledgments

- **World Health Organization (WHO)** for the Global Health Observatory data
- **Kaggle** and dataset contributors (Lasha Gochiashvili, KumarRajarshi)
- Course instructors for guidance and project requirements