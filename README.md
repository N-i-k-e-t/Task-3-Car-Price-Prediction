# Car Price Prediction

## Internship Details

* **Company:** The Black Pearls
* **Internship Period:** June 15, 2024 - July 15, 2024 

## Introduction

This project focuses on building a machine learning model to predict car prices using various features such as year, mileage, and condition.

**Business Context:** This project is relevant to the automotive industry, particularly for businesses involved in car sales, valuation, or price prediction.  Accurate car price prediction can assist in:

* **Setting Competitive Prices:**  Helping businesses optimize pricing strategies for used cars.
* **Estimating Market Value:**  Providing insights for car buyers and sellers.
* **Inventory Management:**  Aiding businesses in making informed decisions about purchasing and selling cars.

## Dataset and Features

* **Data Source:**  The dataset used in this project is "car data.csv". (**Important:** Replace this with the actual source if it's public, or provide a general description if it's internal company data). 
* **Features:**
    * **Year:** Year of manufacture (numerical)
    * **Present_Price:** Current market price of the car (numerical)
    * **Driven_kms:** Total kilometers driven (numerical)
    * **Fuel_Type:** Type of fuel used (categorical)
    * **Selling_type:** Whether the car is new or used (categorical)
    * **Transmission:** Type of transmission (categorical)
    * **Selling_Price:** The target variable - the price at which the car was sold (numerical)
* **Data Preprocessing:**
    * **Missing Values:**  Missing values in 'Present_Price' were filled with the mean value of the column.
    * **Categorical Encoding:**  'Fuel_Type', 'Selling_type', and 'Transmission' were encoded numerically using Label Encoding.
    * **Irrelevant Feature Removal:** The 'Car_Name' feature was removed as it was deemed not relevant to price prediction.
    * **Feature Scaling:**  'Present_Price' and 'Driven_kms' were scaled using StandardScaler to normalize their ranges.

## Methodology

* **Approach:** This project employed a supervised machine learning approach to predict car prices using regression algorithms.
* **Algorithms:**
    * **Random Forest Regressor:** An ensemble method combining multiple decision trees.
    * **Gradient Boosting Regressor:**  Another ensemble technique that builds trees sequentially, each correcting the errors of the previous one.
    * **Support Vector Regression (SVR):** A powerful algorithm that finds the best-fitting line to predict values.
* **Model Selection:** A Grid Search with 5-fold cross-validation was performed for the Random Forest model to tune hyperparameters and minimize mean squared error (MSE). The model with the lowest MSE and highest R-squared score was then selected as the best model. 

## Results and Evaluation

The following table summarizes the performance of the trained regression models:

| Model                  | Mean Squared Error (MSE) | R-squared |
|-------------------------|--------------------------|-----------|
| Random Forest           | 0.744                    | 0.968     |
| Gradient Boosting       | 0.802                    | 0.965     |
| Support Vector Regression | 24.392                   | -0.059    |

**Key Findings:**

* **Random Forest** emerged as the best-performing model, exhibiting the lowest MSE (0.744) and the highest R-squared value (0.968).  
* Both Random Forest and Gradient Boosting demonstrated strong predictive capabilities with R-squared values above 0.96, indicating they can explain over 96% of the variance in car prices. 
* Support Vector Regression performed poorly on this dataset, suggesting it might not be the most suitable algorithm for this particular problem.

**Visualizations:**  (Include a link to the generated bar charts here if you have them in the repository or elsewhere)

## Conclusion

* **Summary:** This project successfully built and compared multiple regression models to predict car prices. The Random Forest model achieved the best performance based on MSE and R-squared metrics. 
* **Business Implications:**  The Black Pearls could leverage the findings and the trained Random Forest model to:
    * Develop internal tools or applications for accurate used car price estimation.
    * Gain a competitive advantage in pricing strategies.
    * Provide valuable insights to customers interested in buying or selling cars.
* **Future Work:** 
    * Investigate the inclusion of additional relevant features, such as car condition, brand reputation, and market demand.
    * Explore more advanced regression techniques or ensemble methods to potentially improve prediction accuracy further.
    * Develop a deployment strategy to integrate the model into a production environment for real-time price predictions.

## Technical Information

* **Installation:**
    * Ensure you have the following libraries installed:
        ```python
        pandas
        numpy
        matplotlib
        seaborn
        scikit-learn
        ```
    * Install them using pip:
        ```bash
        pip install pandas numpy matplotlib seaborn scikit-learn
        ```
* **How to Run:**
    1. Save the code as a Python file (e.g., `car_price_prediction.py`).
    2. Replace `"car data.csv"` with the actual path to your dataset. 
    3. Run the code from your terminal using: `python car_price_prediction.py` 

**Note:** This README assumes you are running the code in an environment where you have access to Google Colab's drive mounting functionality. If running locally, remove or adjust that part of the code.
