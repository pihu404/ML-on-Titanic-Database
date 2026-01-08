1. Data Collection

Loading dataset from an external source (CSV file using URL).

Understanding structured tabular data.

2. Exploratory Data Analysis (EDA)

Viewing initial records using head().

Understanding dataset structure and attributes.

3. Missing Value Analysis

Detecting missing (null) values in each column.

Importance of handling incomplete data to avoid biased results.

4. Data Cleaning

Duplicate Detection: Identifying repeated records.

Duplicate Removal: Eliminating redundant rows to maintain data integrity.

5. Missing Value Imputation

Mean Imputation: Replacing missing numerical values (Age) with mean.

Mode Imputation: Replacing missing categorical values (Embarked) with most frequent value.

Purpose: Ensure dataset completeness.

6. Categorical Data Encoding

Converting categorical variables into numerical form.

Use of Label Encoding for:

Gender (Sex)

Port of Embarkation (Embarked)

Required because ML models work only with numerical data.

7. Feature Scaling / Normalization

Standardizing numerical features using StandardScaler.

Transforms data to zero mean and unit variance.

Helps in faster convergence and fair feature comparison.

8. Feature Selection

Selecting relevant numerical features (Age, Fare).

Avoiding irrelevant or redundant attributes.

9. Data Sorting

Sorting records based on Fare in descending order.

Helps identify high-value observations.

10. Statistical Filtering

Filtering passengers based on condition (Fare > average Fare).

Use of conditional logic for subgroup analysis.

11. Feature Engineering

Creating a new derived feature (AgeGroup).

Binning continuous data into categorical intervals.

Improves interpretability and pattern recognition.

12. Data Visualization

Count Plot:

Visual representation of survival distribution.

Histogram with KDE:

Distribution analysis of Fare.

Understanding skewness and spread.

13. Descriptive Statistics

Mean calculation for Fare.

Understanding central tendency.

14. Data Transformation Pipeline

Sequential steps:

Cleaning → Encoding → Scaling → Feature Creation → Visualization

Forms the foundation of Machine Learning workflows.

15. Supervised Learning Readiness

Preparing cleaned and transformed data suitable for:

Classification models

Prediction tasks
