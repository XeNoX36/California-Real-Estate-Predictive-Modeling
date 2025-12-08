# Analystic Report

The analysis follows a full machine learning workflow:  

Data cleaning & preprocessing  

Outlier detection and removal (using Interquartile Range, IQR)  

Feature engineering  

Exploratory data analysis (EDA)  and Visualizations

Multicollinearity treatment  

Model building and evaluation  

**1. Data Exploration**  

The dataset contains typical housing-related features:  

Median income  

House age  

Rooms and bedrooms  

Population & households  

Latitude & longitude  

Ocean proximity (categorical)   

Median house value (target)  

**2. Data Cleaning & Preprocessing**  

- Outlier Removal — Interquartile Range (IQR)  
Outliers were identified and removed for:

Median income  

Housing age  

Population  

Rooms per household  

This step improved model stability by reducing extreme distortions in the data distribution.  

- Handling Missing Values  
Missing values in total_bedrooms were handled through imputation (median strategy).  

- Categorical Variable Encoding  
The categorical feature "ocean_proximity" was transformed using one-hot encoding, creating dummy variables to allow the model to learn regional effects.  

**3. Multicollinearity Treatment**
A correlation heatmap revealed strong multicollinearity between:  

total_bedrooms  
total_rooms  
households  

To avoid inflated coefficient variance in linear models, total_bedrooms was dropped, reducing redundancy and improving model interpretability.  

**4. Feature Engineering**
New features included:  

Rooms_per_household  

Bedrooms_per_room  

Population_per_household  

These ratios captured more meaningful relationships than raw totals.  

**5. Visualized Reports**  
Observed house values vs Predicted house values:  

![](https://github.com/XeNoX36/California-Real-Estate-Predictive-Modeling/blob/main/California%20Housing/Observed%20vs%20Predicted.png)  

Outlier Analysis on Median Income:  

![](https://github.com/XeNoX36/California-Real-Estate-Predictive-Modeling/blob/main/California%20Housing/Outliers%20Anaylsis%20in%20M-Income.png)  

Overall Correlation Heatmap:  

![](https://github.com/XeNoX36/California-Real-Estate-Predictive-Modeling/blob/main/California%20Housing/heatmap.png)  

Median Housing Value Distribution: 

![](https://github.com/XeNoX36/California-Real-Estate-Predictive-Modeling/blob/main/California%20Housing/median%20hv%20distr.png)  

**6. Modeling Approach**
- Train-Test Split  
Dataset split into:  

80% training  
20% testing  

- Model Used  
A Linear Regression model was implemented to predict median house value.  

- Model Evaluation Metrics  
The following metrics were computed:  

Mean Squared Error (MSE)  
Root Mean Squared Error (RMSE)  
R² Score  

**Key Findings and Insights**
A. Strongest Drivers of Home Value  
Median income is the most significant predictor — higher-income communities have significantly higher home values.  
Latitude and longitude emphasize the coastal pricing premium.  

Rooms per household positively influences housing prices, reflecting larger and more desirable properties.  

Ocean proximity categories show:  

Near ocean and Island properties command significantly higher prices.  

Inland regions have the lowest valuations.  

B. Influence of Population & Density  

Areas with extremely high population density showed diminished house values, pointing to overcrowded, less desirable communities.  

**Recommendations & Business Impact**  
- The model provides a data-driven pricing strategy for real estate developers.
- 
- Government agencies can use insights for urban planning and housing affordability policies.  

- Real estate firms gain a predictive tool to estimate housing prices and optimize investments.  

- Banks and lenders can leverage the model for mortgage risk assessment.
