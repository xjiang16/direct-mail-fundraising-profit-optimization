# Direct Mail Fundraising Profit Optimization

## Overview
This project applies machine learning to improve donor targeting for a direct-mail fundraising campaign. The objective is not simply to predict who will donate, but to maximize expected net profit by balancing mailing costs against expected donation value.

Using historical donor data from a national veterans’ organization, I built and compared multiple classification models and selected decision thresholds based on business impact rather than accuracy alone.

## Business Problem
Direct-mail campaigns often have very low response rates.

- Response rate: 5.1%  
- Average donation: $13.00  
- Mailing cost: $0.68 per person  

Sending mail to everyone is not profitable. This project focuses on identifying high-value targets to improve return on investment (ROI).

## Project Objectives
- Predict donor vs. non-donor outcomes
- Compare multiple classification approaches
- Address business constraints using asymmetric cost evaluation
- Select a model and threshold that maximize expected net profit
- Generate predictions for future fundraising targets

## Approach
- Performed exploratory data analysis (EDA) to understand donor behavior  
- Handled categorical variables and data preprocessing  
- Reduced multicollinearity using correlation analysis and VIF  
- Built and compared multiple models:
  - Logistic Regression  
  - Random Forest  
  - XGBoost  
- Evaluated models using profit-based metrics, not just accuracy  
- Tuned classification thresholds to maximize expected net profit

## Key Insight
The best model is not necessarily the one with the highest accuracy.

By incorporating business costs into evaluation, the optimal model and decision threshold change significantly, leading to better real-world outcomes.

## Dataset
- data/fundraising.csv: historical donor data  
- data/future_fundraising.csv: unseen data for prediction  
- data/submission.csv: final predicted donor labels  

The training data contains 3,000 observations and 22 variables. The dataset was balanced for modeling, while the business framing reflects the original low-response campaign environment.

## Repository Structure
```text
direct-mail-fundraising/
├── data/
│   ├── fundraising.csv
│   ├── future_fundraising.csv
│   └── submission.csv
├── notebooks/
│   ├── model_analysis.Rmd
│   └── experiments.Rmd
├── README.md
└── .gitignore
```

## How to Run
1. Open notebooks/model_analysis.Rmd in RStudio  
2. Install required packages:
   install.packages(c("caret", "randomForest", "xgboost", "pROC"))
3. Run the notebook to reproduce the analysis and results  

## Key Learnings
- Aligning machine learning with business objectives  
- Handling imbalanced classification problems  
- Using cost-sensitive evaluation instead of accuracy alone  
- Comparing multiple models and tuning decision thresholds  

## Future Improvements
- Deploy model as a prediction API  
- Add automated threshold optimization  
- Build a dashboard for campaign decision-making  
