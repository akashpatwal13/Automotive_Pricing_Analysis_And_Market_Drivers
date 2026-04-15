Automotive_Pricing_Analysis_And_Market_Drivers
A data-driven analysis of automotive pricing that identifies key market drivers using statistical testing and linear regression. This project translates technical vehicle specifications into actionable insights to support optimized pricing strategies and market positioning.

Technical Documentation
This repository contains a comprehensive data science workflow designed to quantify the drivers of vehicle pricing. While the associated Executive Summary details the business implications, this document outlines the technical methodology and statistical rigor used to derive those insights.

1. Technical Overview
The project utilizes the ‘UCI Machine Learning’ Repository's Automobile dataset to build a predictive framework for market valuation. The primary objective was to move beyond descriptive statistics into inferential analysis and predictive modeling.

Data Pipeline and Engineering
1. Data Cleaning and Imputation
Raw data often contains missing values (indicated as '?' in the source). The following steps were taken to ensure data integrity:
(a) Numeric Imputation: Columns like `normalized_losses` and `horsepower` were imputed using the median to maintain the central tendency while remaining robust against outliers.
(b) Categorical Imputation:  Missing values in `num_doors` and `fuel_system` were handled using the mode (most frequent value).
Datatype Conversion: Ensuring numeric strings were converted to floats/ints to allow for mathematical operations.


2. Feature Scaling
To ensure that features with larger ranges (like `curb_weight`) did not disproportionately influence the model compared to smaller ranges (like `bore`), two scaling techniques were applied:
(a) Z-score Standardization (StandardScaler): Centers data around a mean of 0 with a standard deviation of 1.
(b) Min-Max Scaling:  Compresses data into a range between 0 and 1.
This preparation is critical for maintaining model stability and interpretability.

Statistical Framework
The project applies inferential statistics to validate assumptions before they are introduced into the machine learning model.

1. Independent Samples T-Test
Used to compare the mean price of two distinct groups (Petrol vs. Diesel). This test determined if the observed price difference was statistically significant or merely a result of random sampling.

2. One-Way ANOVA
Used to compare mean prices across three or more categories (Front-Wheel, Rear-Wheel, and Four-Wheel Drive). The test evaluates whether at least one group mean is statistically different from the others.

3. Chi-Square Test of Independence
Conducted to examine the relationship between two categorical variables (`body_style` and `drive_wheels`). This test identified hidden patterns in how manufacturers "bundle" vehicle features.

Model Development: Linear Regression
The predictive component of the project was built using a Multiple Linear Regression model via Scikit-Learn.
1. Feature Selection
Four primary features were selected based on correlation analysis: `horsepower`, `engine_size`, `curb_weight`, and `city_mpg`.

2. Model Evaluation
The dataset was split into training and testing sets (80/20) to evaluate the model on unseen data.
(a) R-Squared ($R^2$): Used to measure the proportion of variance in the dependent variable (price) explained by the independent variables.
(b) Root Mean Squared Error (RMSE): Used to quantify the average magnitude of the prediction error.

Repository Structure
(a)	Data_wrangling.ipynb: This notebook implements the end-to-end data preparation pipeline, including missing value imputation, feature engineering, and dimensional scaling to ensure a high-integrity dataset for modeling.

(b)	Analysis.ipynb: This notebook executes the core exploratory data analysis, statistical hypothesis testing, and predictive modeling to identify and quantify the primary factors influencing automotive market value. 

(c)	 cleaned_auto_data_final.csv: The processed dataset ready for visualization or further modeling.

(d)	 Images.ppt: Contains all generated plots, including the correlation heatmap and regression visuals.

(e)	Executive Summary: Automotive Pricing Analysis & Market Drivers.pdf: This document provides a high-level strategic overview of the analysis, translating technical statistical results into actionable business insights.


Environment and Dependencies
The project was developed in a Python 3.x environment. The following libraries are required to replicate the analysis:
(a) Data Manipulation: pandas, numpy
(b) Visualization: matplotlib, seaborn
(c) Statistics:  scipy.stats
(d) Machine Learning: scikit-learn

To install all dependencies, execute:
`pip install -r requirements.txt`


<img width="451" height="695" alt="image" src="https://github.com/user-attachments/assets/ef2733f9-9e3a-4d60-b0ec-e1d06687ef05" />
