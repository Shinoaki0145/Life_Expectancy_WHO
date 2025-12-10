# Individual Reflections Each group member should write a personal reflection covering: 
**Challenges & Difficulties Encountered:**
- What specific obstacles did you face? (technical, analytical, conceptual) 
- How did you overcome them? 
- What was most challenging and why? Learning & Growth:
- What have you learned? (technical skills, analytical approaches, domain knowledge)
- What surprised you most?
- How has this project shaped your understanding of data science?

---

## VIET

### **Challenges & Difficulties Encountered**

#### Technical Obstacles:

1. **Multicollinearity in Regression Analysis (Question 1)**
   - Schooling and GDP are often correlated (wealthier countries tend to have better education), which could make regression coefficients unstable
   - *Solution:* Performed multicollinearity diagnostics first, found correlation was acceptable (~0.34 for developed, moderate for developing countries), allowing standard OLS regression to proceed

2. **Data Preprocessing Complexity (Both Questions)**
   - Missing values across multiple health indicators
   - Extreme outliers in GDP, HIV rates, and infant mortality
   - *Solution:* Used median imputation for numerical features, log transformation for GDP (`log1p`) to normalize skewed distributions

3. **Stratified Sampling Implementation (Question 3)**
   - Had to ensure regional representation in train/test splits to avoid bias (e.g., test set only containing African or European countries)
   - *Solution:* Implemented `StratifiedShuffleSplit` based on Region column, verified distribution differences were <5%

4. **Feature Selection Dilemma (Question 3)**
   - Mortality-related features (infant deaths, adult mortality) were highly predictive but essentially "proxies" for the target variable, creating data leakage concerns
   - *Solution:* Conducted ablation analysis—removing mortality proxies to understand true root causes (economic and social determinants)

#### Analytical/Conceptual Obstacles:

1. **Interpreting Preston Curve Theory (Question 1)**
   - Understanding that GDP-life expectancy relationship is logarithmic, not linear—required theoretical background reading
   - Identifying the "saturation point" (~$20,000 GDP) where additional wealth has diminishing returns

2. **Balancing Model Accuracy vs. Interpretability (Question 3)**
   - Random Forest achieves high R² but is a "black box"; needed to extract feature importance for policy relevance
   - Comparing tree-based (global patterns) vs. instance-based (KNN local patterns) approaches

#### Most Challenging Aspect:
**Transforming statistical findings into actionable policy insights.** It's one thing to calculate that education has coefficient β₁=0.8 in developing countries; it's another to translate this into "governments should prioritize schooling over pure GDP growth for sustainable health improvements."

---

### **Learning & Growth**

#### Technical Skills Learned:

| Skill | Application in Project |
|-------|------------------------|
| **OLS Regression with diagnostics** | Multicollinearity check, coefficient interpretation, p-values |
| **Log Transformation** | Linearizing Preston Curve relationship |
| **Stratified Train-Test Split** | Using `StratifiedShuffleSplit` for fair regional representation |
| **Random Forest & KNN** | Ensemble methods vs. instance-based learning comparison |
| **Feature Importance Analysis** | Identifying which health/economic/social factors matter most |
| **Data Visualization** | Seaborn heatmaps, scatter plots with regression lines, box plots |

#### Analytical Approaches Learned:

1. **Comparative Analysis Framework**: Separating developed vs. developing countries to reveal different dynamics (e.g., education has 2x higher impact in poor countries)
2. **Ablation Studies**: Removing variables systematically to understand true causality vs. correlation
3. **Correlation vs. Causation Thinking**: GDP growth (-0.11) has much weaker correlation with mortality reduction than vaccination coverage (-0.43)

#### Domain Knowledge Gained:

- **Preston Curve** economics: Wealth buys health, but only up to a point (~$20,000 GDP threshold)
- **"Geographical Penalty"**: Africa faces unique challenges (tropical diseases, conflict) that prevent converting low GDP into high life expectancy, unlike Asia or Latin America
- **Diminishing Returns in Public Health**: Once vaccination coverage exceeds ~90%, additional healthcare spending yields smaller gains

#### What Surprised Me Most:

> *"Poor countries can nearly match rich countries in life expectancy through strategic investments—the gap between High Income (91.1% vaccination) and Low GDP Overachievers (88.6%) was only 2.5 percentage points. Money isn't the limiting factor; strategic health policy is."*

> *"HIV rates in some low-income 'overachiever' countries (0.13/1000) were lower than wealthy countries (0.20/1000)—discipline in disease control can outperform economic advantage."*

---

### **How This Project Shaped My Understanding of Data Science**

1. **Data science is about storytelling, not just modeling.** The Random Forest achieved high R², but the real value came from translating feature importance into the policy recommendation: "Prioritize vaccination and education over expensive high-tech healthcare facilities."

2. **Domain knowledge is essential.** Without understanding Preston Curve theory or public health economics, the log transformation of GDP would seem arbitrary, and the "saturation point" finding would be meaningless.

3. **Preprocessing decisions shape conclusions.** The choice to use stratified sampling by Region, handle missing values via median imputation, and remove mortality proxy variables fundamentally affected what insights emerged.

4. **Real-world data is messy and political.** Countries with the poorest outcomes often have the least complete data (survivorship bias). Our "overachiever" findings might be slightly optimistic because the worst-off nations couldn't report.

5. **Comparison reveals more than individual analysis.** Analyzing developed and developing countries separately revealed that education coefficient is 2x higher in poor countries—a finding invisible in aggregate analysis.

---