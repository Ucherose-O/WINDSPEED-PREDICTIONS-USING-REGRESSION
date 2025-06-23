# WINDSPEED-PREDICTIONS-USING-REGRESSION
 Wind Speed & Energy Output Analysis

Overview

This project explores the relationship between wind speed measurements at various altitudes and energy output. The goal is to apply exploratory data analysis (EDA), regression modeling, and outlier detection to gain insights and build a predictive model.

1. Exploratory Data Analysis (EDA)

Visualized scatter plots between wind_speed48M and Output.

Computed summary statistics:

Mean, variance, standard deviation, min, max for all numeric columns.

Plotted correlation heatmaps:

sns.heatmap(df.corr(numeric_only=True), annot=True)

Combined x and y to inspect full numeric relationships.

2. Data Visualization

Plotted wind speed vs output with outlier color coding.

Used IQR and Z-score methods to visually detect outliers.

Created custom scatter plots to highlight large prediction errors (color-coded).

3. Regression Modeling

Trained a Linear Regression model using scikit-learn.

Predicted on x_test, evaluated using R² score.

Visualized actual vs predicted output.

4. Polynomial Regression

Iterated through polynomial degrees to fit models using PolynomialFeatures.

Plotted each polynomial model's predictions:

for degree in range(1, N+1):
    PolynomialFeatures(degree)...

5. Error Analysis

Calculated absolute errors.

Flagged predictions with error > ±8000.

Visualized these outliers with black (high error) and green (low error) points.

6. Outlier Detection

IQR Method:

Q1 = y.quantile(0.25)
Q3 = y.quantile(0.75)
IQR = Q3 - Q1
outliers = (y < Q1 - 1.5*IQR) | (y > Q3 + 1.5*IQR)

Z-score Method:

z = (y - y.mean()) / y.std()
outliers = abs(z) > threshold

Binned detection using standard deviation within x-axis segments.

Insights

Strong correlation between wind speeds at different heights.

Output correlates highly with wind_speed48M.

Polynomial regression improves fit over linear.

Outlier analysis crucial for identifying poor model performance.

Tools

pandas, numpy for data handling

matplotlib, seaborn for visualization

scikit-learn for modeling and evaluation
