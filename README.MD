



\# Life Expectancy Prediction using Machine Learning



\## Project Overview



This project builds and evaluates machine learning models to predict \*\*Life Expectancy\*\* for countries using economic, demographic, and geographic indicators from the \*\*World database\*\*.



The goal is to explore how factors such as \*\*population, economic output (GNP), population density, and government type\*\* relate to life expectancy and to build predictive models capable of estimating life expectancy from these indicators.



The dataset contains \*\*236 observations and 15 features\*\*, representing country-level information.



\---



\# Dataset



The dataset was retrieved from a \*\*MySQL world database\*\* using Python.



Key variables include:



| Feature           | Description                      |

| ----------------- | -------------------------------- |

| Region            | Geographic region of the country |

| SurfaceArea       | Total land area                  |

| IndepYear         | Year of independence             |

| Population        | Total population                 |

| GNP               | Gross National Product           |

| GNPOld            | Previous GNP value               |

| GovernmentForm    | Type of government               |

| Population\_Desity | Population per square kilometer  |



Target variable:



\*\*LifeExpectancy\*\*



\---



\# Feature Engineering



Several derived features were created to capture economic and demographic relationships:



\* \*\*AVG\_GNP\*\* – average of current and previous GNP

\* \*\*GNP\_growth\*\* – economic growth rate

\* \*\*per\_capita\_GNPOld\*\* – GNP per person

\* \*\*GNP\_per\_sqkm\*\* – economic output per land area

\* \*\*Density\_perGNP\*\* – interaction between population density and economic indicators



These features help capture \*\*structural economic differences between countries\*\*.



\---



\# Data Preprocessing



The following preprocessing steps were performed:



\* Missing value imputation

\* Correction of negative or invalid independence years

\* Handling of zero values in economic indicators

\* Feature scaling using \*\*StandardScaler\*\*

\* Encoding categorical variables using \*\*OneHotEncoder\*\*



A \*\*ColumnTransformer\*\* was used to ensure proper preprocessing for both numerical and categorical variables.



\---



\# Machine Learning Pipeline



A scikit-learn \*\*Pipeline\*\* was implemented to combine preprocessing and modeling steps.



The workflow includes:



1\. Data preprocessing

2\. Model training

3\. Cross-validation

4\. Hyperparameter tuning

5\. Model evaluation



\---



\# Models Evaluated



Several regression models were compared:



\* Decision Tree Regressor

\* Random Forest Regressor

\* Gradient Boosting Regressor

\* XGBoost Regressor



Model comparison was performed using \*\*cross-validation\*\*.



\---



\# Hyperparameter Tuning



Two optimization approaches were used:



\### GridSearchCV



Applied to \*\*Gradient Boosting Regressor\*\* to identify optimal tree depth, number of estimators, and split parameters.



\### RandomizedSearchCV



Applied to \*\*XGBoost Regressor\*\* to efficiently explore a larger hyperparameter space.



\---



\# Model Performance



\### Gradient Boosting Regressor



| Metric              | Score |

| ------------------- | ----- |

| Cross-Validation R² | 0.71  |

| Train R²            | 0.99  |

| Test R²             | 0.65  |



Best Parameters:



\* max\_depth: 2

\* n\_estimators: 300

\* min\_samples\_leaf: 3

\* min\_samples\_split: 5

\* max\_features: 0.7



\---



\### XGBoost Regressor



| Metric              | Score |

| ------------------- | ----- |

| Cross-Validation R² | 0.70  |

| Train R²            | 0.98  |

| Test R²             | 0.65  |



Best Parameters include optimized learning rate, subsampling, and regularization.



\---



\# Visualization



Model behavior was analyzed using:



\* Pairwise feature relationships

\* Predicted vs Actual comparison plot

\* Hyperparameter tuning curves



These visualizations help diagnose \*\*model fit and prediction behavior\*\*.



\---



\# Key Findings



\* Economic indicators such as \*\*GNP and population density\*\* strongly correlate with life expectancy.

\* \*\*Gradient Boosting and XGBoost\*\* performed best among the tested models.

\* The model explains approximately \*\*65% of the variance in life expectancy\*\* on unseen data.



Given the relatively small dataset size (236 samples), this level of performance is considered reasonable.



\---



\# Technologies Used



\* Python

\* Pandas

\* NumPy

\* Scikit-learn

\* XGBoost

\* Seaborn

\* Matplotlib

\* MySQL

\* SQLAlchemy



\---



\# Limitations



\* The dataset is relatively small, which can lead to model overfitting.

\* Some economic indicators may be highly correlated.

\* Additional health and social indicators could improve predictive power.



\---



\# Future Improvements



Potential improvements include:



\* Additional feature engineering

\* Advanced model interpretation (e.g., SHAP analysis)

\* Incorporating health and education indicators

\* Expanding dataset size



\---



\# Author



\*\*Obiaeli Chika\*\*



Machine Learning Project





