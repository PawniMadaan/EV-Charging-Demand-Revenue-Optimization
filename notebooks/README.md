EV Charging Demand & Revenue Optimization Using Machine Learning
Project Overview
Electric vehicle adoption is increasing the demand for reliable and efficient charging infrastructure. Predicting charging demand can help charging-station operators understand demand patterns, plan resources, and make informed operational decisions.

This project develops a machine-learning workflow to predict hourly EV charging volume using historical charging data. The predictions can support further analysis of charging infrastructure planning and revenue-related decisions.

Objectives
Understand and analyze EV charging-demand data.
Perform data preprocessing and exploratory data analysis.
Engineer temporal and historical demand features.
Train regression models to predict charging volume.
Compare model performance using evaluation metrics.
Explore how demand predictions can support charging-station planning and revenue analysis.
Dataset
The project uses the UrbanEV dataset from Shenzhen, China.

Dataset period: September 2022 to February 2023.

The ML workflow uses a prepared hourly system summary containing 4,344 hourly records.

Dataset source:
https://github.com/IntelligentSystemsLab/UrbanEV

The original dataset is organized around urban traffic zones. The project uses a prepared hourly summary for system-level demand prediction.

Methodology
The machine-learning workflow includes:

Dataset inspection and understanding.
Date-time conversion and chronological sorting.
Temporal feature engineering.
Lag-feature generation.
Rolling-window feature generation.
Chronological train-test split.
Regression model training.
Model evaluation and comparison.
Prediction export and model saving.
Machine Learning Models
The following regression algorithms were evaluated:

Linear Regression
Decision Tree Regressor
Random Forest Regressor
Two prediction targets were used:

Total charging volume
11 kW reference charging volume
Feature Engineering
The engineered features include:

Hour
Day of week
Month
Weekend indicator
Peak-hour indicator
Previous-hour demand
Previous-day demand
Previous-week demand
24-hour rolling mean
The peak-hour indicator uses predefined time periods: 7–10 AM and 5–9 PM, and is an assumption used in the project.

Model Evaluation
The models were evaluated using:

Mean Absolute Error (MAE)
Root Mean Squared Error (RMSE)
R-squared (R²)
Random Forest achieved the best performance among the tested machine-learning models for both prediction targets.

Total Charging Volume
Model	MAE	RMSE	R²
Linear Regression	5502.82	7141.37	0.9070
Decision Tree	5355.16	7622.38	0.8940
Random Forest	3884.28	5412.07	0.9466
11 kW Reference Charging Volume
Model	MAE	RMSE	R²
Linear Regression	1250.91	1599.68	0.9326
Decision Tree	1360.97	1797.08	0.9149
Random Forest	961.69	1294.68	0.9559
Project Structure
EV-Charging-Demand-Optimization/
├── README.md
├── notebooks/
├── outputs/
├── models/
├── report/
└── requirements.txt
Team Contributions
Data Analyst: Dataset understanding, preprocessing, exploratory data analysis, and preparation of the hourly summary.
ML Developer: Feature engineering, model training, evaluation, prediction generation, model comparison, and model saving.
Business Analyst: Revenue analysis, business interpretation, optimization scenarios, and dashboard-related insights.
Limitations
The models are trained on data from Shenzhen, China.
The model's performance in other geographical regions requires local data and validation.
The unit of the charging-volume target was not independently verified.
The peak-hour indicator is based on predefined time periods.
The current evaluation represents rolling one-hour-ahead prediction when previous observations are available.
Revenue optimization requires additional analysis of tariffs, charging capacity, and operational constraints.
Conclusion
The project demonstrates the use of machine learning for hourly EV charging-volume prediction. Random Forest achieved the best test performance among the evaluated models for both targets.

The predicted demand can serve as an input for further charging-station planning and revenue analysis.

Technologies Used
Python
Pandas
NumPy
Matplotlib
Seaborn
Scikit-learn
Jupyter Notebook
Overleaf / LaTeX
GitHub
Power Bi
