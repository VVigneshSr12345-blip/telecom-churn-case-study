Telecom Churn Prediction Case Study
Problem Statement

In the highly competitive telecom industry, customers frequently switch between service providers, leading to an average churn rate of 15-25% annually. Retaining customers is significantly more cost-effective than acquiring new ones, making churn prediction crucial for telecom companies.

This project aims to analyze customer behavior, identify high-risk churners, and build predictive models to help telecom firms proactively retain valuable customers.
Defining Churn

Telecom companies operate under two primary payment models:

    Postpaid: Customers receive a monthly bill and actively notify the provider before switching. Churn is easily identifiable.
    Prepaid: Customers pay in advance and can stop using services without notice, making churn detection more complex.

Since prepaid models dominate Indian and Southeast Asian markets, this study focuses on prepaid customer churn prediction using a usage-based definition.
Churn Definition

We define a customer as churned if they have:

    No outgoing or incoming calls (total_ic_mou_9 and total_og_mou_9)
    No mobile internet usage (vol_2g_mb_9 and vol_3g_mb_9)
    for an extended period in the churn phase (month 9).

Targeting High-Value Customers

Since 80% of revenue comes from the top 20% of customers, retaining high-value users is a top priority. We define high-value customers as those who have recharged above the 70th percentile of average recharge amounts in the good phase (months 6 & 7).
Customer Lifecycle Phases

Customers typically transition through three phases before churning:

    Good Phase (Months 6 & 7): Normal usage with no churn risk.
    Action Phase (Month 8): Behavior shifts due to dissatisfaction, competitive offers, or service issues. Early detection is critical.
    Churn Phase (Month 9): Customers stop using services, marking churn.

At the time of prediction, churn phase data is not available, so we must forecast churn using the first three months.
Data and Preparation

The dataset contains customer-level data over four months (June–September), encoded as months 6, 7, 8, and 9.
Data Processing Steps:

    Feature Engineering: Derive new features that indicate churn risk.
    Filter High-Value Customers: Retain only users in the top 30% of revenue contributors.
    Tag Churners: Assign churn labels based on zero call and internet usage in month 9.
    Remove Churn Phase Data: Drop all month-9 attributes to ensure realistic predictions.

Predictive Modeling

We will build machine learning models to achieve two key objectives:

    Predict High-Value Customer Churn:
        Identify users likely to churn so retention strategies can be implemented.
        Handle class imbalance (since churners are a small fraction of the total).
        Use PCA (Principal Component Analysis) to reduce dimensionality before model training.

    Identify Key Churn Predictors:
        Use interpretable models (Logistic Regression, Decision Trees) to pinpoint the most important churn indicators.
        Handle multi-collinearity to ensure meaningful insights.
        Visualize key churn predictors using summary tables and charts.

Modeling Approach:

    Preprocess Data: Convert formats, handle missing values, and scale features.
    Exploratory Analysis: Identify trends and churn patterns.
    Feature Engineering: Create meaningful variables that indicate churn risk.
    Dimensionality Reduction: Apply PCA to improve efficiency.
    Train Multiple Models: Compare Logistic Regression, Decision Trees, Random Forests, and other techniques.
    Handle Class Imbalance: Use resampling methods such as SMOTE (Synthetic Minority Over-sampling Technique).
    Evaluate Models: Use precision, recall, F1-score, and AUC-ROC to prioritize identifying churners accurately.
    Deploy the Best Model: Optimize hyperparameters for real-world implementation.

Business Impact and Recommendations

Based on the analysis, we will recommend targeted retention strategies such as:

    Personalized offers for at-risk customers.
    Loyalty rewards and discounts for high-value users.
    Proactive customer support to address service issues early.
    Competitor benchmarking to align pricing and features with market trends.

Conclusion

This project will provide a data-driven approach to reducing telecom churn by:
 Predicting high-value customer churn before it happens.
 Identifying key churn indicators to guide business decisions.
 Optimizing retention strategies for maximum revenue impact.
