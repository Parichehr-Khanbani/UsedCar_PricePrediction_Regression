# UsedCar_PricePrediction_Regression
***A complete ML regression project to predict used car prices, including data preprocessing, feature transformation, model tuning, and evaluation***
<p align="center">
  <img src="https://github.com/Parichehr-Khanbani/UsedCar_PricePrediction_Regression/blob/main/assets/car.webp" alt="Car Price Banner" width="100%">
</p>

# **1.Project Overview**

This project develops and evaluates a machine learning model to predict the selling price of used vehicles based on vehicle characteristics such as age, present price, mileage, and fuel type. The workflow emphasizes robust preprocessing, careful handling of outliers, and thorough model evaluation, ensuring strong generalization performance on unseen data.

# **2.Dataset**

The dataset contains 301 records and includes both numerical and categorical attributes commonly associated with vehicle valuation:

| **Column Name**              | **Description**|
| ---------------------------- | -------------------------------------------------------------- |
| **Kms_Driven**               | Total kilometers the car has been driven (indicator of usage). |
| **Fuel_Type**                | Type of fuel used: Petrol, Diesel, or CNG.                     |
| **Seller_Type**              | Seller category: Individual or Dealer.                         |
| **Transmission**             | Transmission type: Manual or Automatic.                        |
| **Owner**                    | Number of previous owners.                                     |
| **Year**                     | Manufacturing year of the car.                                 |
| **Present_Price**            | Current market/initial purchase price of the car.              |
| **Selling_Price** *(Target)* | Final selling price of the car.                                |


# **3.Methodology**

**3.1. Data Preprocessing**

*  Feature Engineering(converting manufacturing year to age which is more informative)
*  One-hot encoding of categorical variables with consistent column alignment
*  Consolidation of ownership categories to reduce sparsity
*  Removal of redundant fuel-type features
*  Feature scaling and normalization using Yeo–Johnson transformation
*  Target variable transformation to stabilize variance and improve model learning

**3.2. Outlier Analysis**

*  Univariate and bivariate outlier detection based on transformed feature space
*  Outliers were retained for modeling and evaluation
*  Outlier flags were preserved for visualization and diagnostic analysis
  
**3.3. Model Training**

*  Multiple regression models evaluated
*  Hyperparameter tuning performed using GridSearchCV
*  Best-performing model selected based on cross-validated 𝑅2 score
* Final pipeline saved and reused for test and unseen data inference

# **4.Model Evaluation**

The final model demonstrates strong predictive performance:

*  High 𝑅2 score on both training and test sets
*  Small and expected generalization gap
*  Residuals centered around zero, indicating a good fit
*  Prediction error increases with price range, largely due to limited high-price samples

 Multiple diagnostic plots were used, including:
*  Actual vs. Predicted values
*  Residuals vs. Predictions
*  KDE distributions (transformed and original scales)
*  Error analysis by price segment

# **5.Prediction on Unseen Data**

The trained pipeline was successfully applied to a new, unseen vehicle instance, with all preprocessing steps applied consistently. Predictions were inverse-transformed back to the original price scale, demonstrating the model’s practical usability and deployment readiness.

# **6.Conclusion**

This project demonstrates a complete, well-structured machine learning pipeline with strong predictive performance and sound statistical reasoning. It highlights best practices in preprocessing, feature engineering, outlier analysis, and model evaluation, making it a solid foundation for real-world regression problems in pricing and valuation domains.
