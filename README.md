# Predicting Used Car Prices

<div align="center">
    <img width="383" alt="image" src="https://github.com/NRUTHVIIK1396/Predictive-pricing-for-used-cars/blob/main/images/kurt.jpeg">
</div>

### Project Overview and Introduction
In the competitive landscape of the used car market, precise pricing plays a vital role in optimizing profits, drawing in customers, and efficiently managing inventory. This project focuses on harnessing data analytics and machine learning to pinpoint the primary factors influencing used car prices and build a predictive model for accurate price forecasting. By doing so, it empowers used car businesses to make data-driven pricing decisions, foster customer confidence, and boost overall business success.

### CRISP-DM Framework
This project follows the CRISP-DM (Cross-Industry Standard Process for Data Mining) framework, a widely recognized methodology that offers a structured and systematic approach to data analysis. The CRISP-DM process is divided into six key phases: Business Understanding, Data Understanding, Data Preparation, Modeling, Evaluation, and Deployment, ensuring a comprehensive and efficient progression throughout the project.

<div align="center">
    <img width="354" alt="image" src="https://github.com/NRUTHVIIK1396/Predictive-pricing-for-used-cars/blob/main/images/crisp.png">
</div>


## Business Understanding

The used car industry is fast-paced and constantly evolving due to a range of influences such as economic conditions and shifting consumer demands. For this business, accurately predicting the value of used vehicles is crucial for several important reasons:

- <b>Efficient Inventory Management:</b> Proper pricing ensures that the business maintains balanced stock levels, preventing excess or shortages in the vehicle inventory.
- <b>Effective Sales Approach:</b> Correctly priced cars can increase market competitiveness, drawing in more buyers and boosting sales figures.
- <b>Building Customer Confidence:</b> Transparent and fair pricing practices foster customer confidence and loyalty over time.
- <b>Financial Accuracy:</b> Reliable price forecasts aid in precise budgeting and financial planning.

Given these points, the primary objective is to uncover the key factors that significantly affect the pricing of used cars. Gaining insight into these factors will allow the business to develop an optimized pricing framework, enhance decision-making capabilities, and improve overall business operations.

### Goals

- <b> Determine Major Price Influencers:</b> Identify the crucial variables that impact the prices of used vehicles, considering both quantitative and qualitative factors (e.g., mileage, vehicle age, make, model, condition, etc.).

- <b>Create a Predictive Model:</b> Develop an advanced model capable of accurately estimating used car prices. This model must be dependable, scalable, and seamlessly adaptable to current business workflows.

- <b> Refine Pricing Strategy:</b> Use insights from the predictive model to fine-tune the pricing strategy. The focus is on setting competitive prices that accurately represent the vehicle’s value while maximizing profitability.

- <b>Support Strategic Choices:</b> Provide actionable insights to guide key decisions related to sourcing, sales, and marketing strategies. This involves analyzing seasonal patterns, identifying high-demand vehicles, and effectively targeting potential customers.

- <b>Enhance Customer Satisfaction:</b> Offer clear and reasonable pricing, improving the buying experience and fostering long-lasting relationships with customers.

- <b>Improve Inventory Efficiency:</b> Leverage price predictions to maintain a balanced vehicle inventory, ensuring the availability of high-demand models without overstocking or understocking.

By accomplishing these goals, the business aims to strengthen its market position, streamline operations, and promote sustainable long-term growth.

## Data Understanding
In the Data Understanding phase, I examined and familiarized myself with a dataset containing 426,880 used car listings. This process involved pinpointing essential variables such as price, year, odometer readings, and categorical attributes like manufacturer, model, and condition. My initial exploration of the data provided insights into its quality, distribution, and the relationships among the variables. This foundation is crucial for the upcoming data preparation and modeling stages within the CRISP-DM framework.

### Data Collection
The dataset consisting of 426,880 used car listings was obtained from Kaggle, a platform celebrated for featuring a variety of datasets provided by the community.

### Data Description

The dataset contains information on 426,880 used cars, with 18 attributes detailing various aspects of each vehicle. Below is a detailed description of each column:

1. **id:** A unique identifier for each car listing.
2. **region:** The geographic region where the car is listed.
3. **price:** The listed price of the car in dollars.
4. **year:** The manufacturing year of the car.
5. **manufacturer:** The manufacturer or brand of the car (e.g., Ford, Toyota).
6. **model:** The model name of the car.
7. **condition:** The condition of the car (e.g., new, like new, excellent, good, fair, salvage).
8. **cylinders:** The number of cylinders in the car's engine.
9. **fuel:** The type of fuel the car uses (e.g., gas, diesel, electric, hybrid).
10. **odometer:** The mileage of the car (distance traveled in miles).
11. **title_status:** The status of the car's title (e.g., clean, salvage, rebuilt).
12. **transmission:** The type of transmission (e.g., automatic, manual).
13. **VIN:** The Vehicle Identification Number, a unique code used to identify individual motor vehicles.
14. **drive:** The type of drivetrain (e.g., 4wd, fwd, rwd).
15. **size:** The size category of the car (e.g., compact, mid-size, full-size).
16. **type:** The type or category of the car (e.g., sedan, SUV, truck).
17. **paint_color:** The exterior color of the car's paint.
18. **state:** The state where the car is listed.

### Data Exploration

During the Data Exploration phase, a detailed analysis was performed to uncover patterns, relationships, and insights within the dataset. The primary activities included:

- **Bivariate Relationship Analysis:** Relationships between pairs of variables, such as price in relation to year and odometer readings, were examined using scatter plots and box plots. This analysis clarified how different features interact and affect the target variable, which is price.

 - **Outlier Detection:** Outliers within numerical features were identified through visualizations like box plots and histograms. The potential influence of these outliers on the overall analysis and modeling processes was also assessed.

- **Distribution Analysis of Variables:** The distributions of critical variables, including price, year, and odometer, were visualized using histograms, density plots, and box plots. This approach facilitated an understanding of the data's spread, helped identify any skewness or kurtosis, and aided in detecting potential outliers while illustrating the overall shape of the data.

- **Assessment of Missing Data:** Columns containing missing values were identified, and the proportion of missing data for each was calculated based on make and model. Heatmaps were utilized to visualize the patterns of missing data, providing insights into the distribution and extent of missingness across the dataset.

- **Analysis of Categorical Variables:** The distribution of categorical variables, such as manufacturer, fuel type, and transmission, was explored using count plots. This analysis yielded insights into the most common categories and their respective frequencies.

- **Correlation Analysis:** Correlation coefficients were calculated to uncover linear relationships among numerical variables. These correlations were visualized through heatmaps and Seaborn pair plots, highlighting significant connections, including those between year and price as well as odometer and price.

- **Summary Statistics Calculation:** Summary statistics for each numerical feature, including the mean, median, standard deviation, minimum, and maximum values, were computed. This analysis provided a comprehensive overview of the data distribution and central tendencies.

These exploratory analyses established a strong foundation for the subsequent data preparation and modeling phases, ensuring a thorough understanding of the dataset and informing decision-making throughout the project.

## Data Preparation

During the Data Preparation phase, the primary goal was to convert the raw dataset into a clean and organized format that is appropriate for modeling. This stage is essential for guaranteeing the precision and dependability of the predictive model. Below is a comprehensive summary of the actions undertaken:

- **Data Cleaning:**
    - **Addressing Missing Values:** Identified the presence of missing values in several columns, including year, manufacturer, model, condition, cylinders, fuel type, odometer readings, title status, transmission type, drive type, size category, car type, paint color, and state.

    - **Managing Outliers:** Outliers were dealt with by either removing them, applying transformations (such as log transformation), or capping extreme values. Specifically, outliers in the year, odometer, and price columns were eliminated using the IQR method.

    - **Eliminating Duplicates:** All duplicate entries were removed from the dataset.

    - **Correcting Data Types:** No adjustments were necessary for data types.

    - **Resolving Inconsistencies:** There were no issues related to inconsistent data (e.g., negative values for age).

    - **Splitting Data into Training and Test Sets:** This step involved dividing the dataset to ensure that a portion of it could be used for training the model while the remainder would be utilized for testing its performance. Conducting a train/test split before feature engineering and modeling is critical to prevent data leakage and to provide an accurate assessment of the model’s effectiveness on unseen data.

- **Prevention of Data Leakage**
    - **Accurate Evaluation**
    - **Ethical Modeling Practices**

- **Feature Engineering / Data Transformation:**
    - **Normalization/Scaling:** Numerical features like price, vehicle age, and odometer readings underwent scaling using methods such as Min-Max scaling to standardize their range, thereby enhancing the performance of machine learning algorithms sensitive to differing scales.

    - **Polynomial Features:** The numerical features of price, vehicle age, and odometer were modified using polynomial feature generation with a degree of 2.

    - **Encoding Categorical Variables:**

        - **Target Encoding:** The make_model variable was encoded through target encoding.
        - **One-Hot Encoding:** Variables such as fuel, transmission, type, and paint color were transformed into numerical format using one-hot encoding.
        - **Ordinal Encoding:** The condition, cylinders, title status, drive type, and size were encoded using ordinal encoding.
    - **Deriving New Features:** New features were created or adjusted from existing ones to improve predictive capabilities. For instance, a derived feature labeled "vehicle age" was created by calculating the difference between the current year and the year of manufacture, providing valuable insights into pricing trends related to depreciation. Additionally, a make_model feature was generated by combining the manufacturer and model columns.

By thoroughly preparing the dataset in this manner, a robust foundation was established for the development and assessment of predictive models aimed at accurately estimating used car prices. This phase not only improved the quality of the data but also facilitated the subsequent stages of modeling, evaluation, and deployment within the CRISP-DM framework. 

## Modeling
During the Modeling phase, the objective was to build a reliable predictive model capable of estimating used car prices based on the refined dataset. The key steps and considerations were as follows:

- **Model Selection:** Several regression models were assessed, including Linear, Ridge, Lasso, and Elastic Net Regression, all chosen for their suitability in predicting continuous variables. These models were evaluated based on their ability to accommodate the dataset's structure, provide interpretability, and deliver high predictive accuracy.

- **Model Training:** The chosen models were trained using the dataset curated during the data preparation stage. Techniques such as grid search and cross-validation were employed to fine-tune model parameters, enhancing performance and mitigating the risk of overfitting.

### Modeling Output
Among the four models, ElasticNet Regression delivers the best performance, demonstrating the lowest RMSE and also has the highest R² score, making it the most appropriate model for this dataset based on these metrics. Both Ridge and Lasso yielded comparable results, suggesting further evaluation with varying alpha values could be beneficial.

**RMSE (Root Mean Squared Error)** = 9589.6535: This metric reflects the average prediction error. In this case, the model's predictions deviate by approximately 9589.6535 units from the actual car prices, on average.

**R² (R-squared)** = 0: Elastic Net also has the highest R² value (-0.0000), which is closer to zero than the other models. Although all R² values are negative, indicating that none of the models perform well in explaining the variance of the target variable, Elastic Net still performs slightly better.

## Evaluation
In the Evaluation phase, the trained models were assessed to verify that they aligned with project goals and business requirements:

**Evaluation Metrics:** Metrics like Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and R-squared (R²) were used to evaluate the prediction accuracy. These metrics helped gauge how closely the models' predicted used car prices matched the actual values.

**Model Validation:** The models were validated on the test dataset, reserved during data preparation, to ensure they generalized well to new, unseen data and were not overfitting to the training data.

**VIF for Multicollinearity:** Variance Inflation Factor (VIF) was calculated to detect multicollinearity among the independent variables. VIF quantifies how much the variance of a regression coefficient increases due to collinearity with other features. A VIF above 10 typically signals high multicollinearity, although even lower values can pose issues depending on the model and context.

  - **Interpretation of VIF Results**
The VIF analysis indicates that several features exhibit infinite (inf) values, pointing to perfect multicollinearity. This occurs when certain features are exact linear combinations of others, making it impossible to estimate their coefficients independently.

**Features with Infinite VIF:**

- **Paint Colors:** All categories for paint color show infinite VIF, indicating perfect collinearity.
- **Vehicle Types:** Categories such as mini-van, hatchback, coupe, etc., have infinite VIF values, signifying perfect multicollinearity.
- **Fuel Types:** Every fuel type category also displays infinite VIF.
- **Transmission Types:** Transmission types exhibit infinite VIF, indicating they are fully collinear with other features.

- **Cross Validation and Hyperparameter Tuning** was performed to evaluate the models.

    - Best Elastic Net Regression: {'alpha': 10.0}, RMSE = 9575.2535
    - Best Ridge: {'alpha': 100.0}, RMSE = 9575.5213
    - Best Lasso: {'alpha': 10.0}, RMSE = 9575.2680

    - Evaluate the best models on the test set
        - Elastic Net Regression: RMSE = 9589.5822, R2 = 0.0000
        - Ridge: RMSE = 9591.3010, R2 = -0.0003
        - Lasso: RMSE = 9589.7797, R2 = -0.0000

## Model Predictions

- **Best Model: ElasticNet with cross-validation**
    - Mean cross-validation score: -0.00013489488781877058
    - Standard deviation of cross-validation score: 0.00016909724467853622
    
- **Permutation Inportance** was used to assess the importance of the coefficients. It didn't make any difference in the performance of the model after removing negative permutation importance coefficients.
    - Elastic Net Regression: RMSE = 9589.5467, R2 = 0.0000
    - Ridge: RMSE = 9589.7044, R2 = -0.0000
    - Lasso: RMSE = 9589.6899, R2 = -0.0000


## Conclusion
This project centered on forecasting used car prices through a systematic approach aligned with the CRISP-DM framework. It began with defining business goals and collecting relevant data, then progressed through detailed data preparation, model development, evaluation, and deployment stages. Below is a summary of key findings and actionable insights:

#### Findings

- Diesel engines are associated with higher prices, with electric and hybrid models contributing positively.
- Convertibles, trucks, and similar vehicle types generally command higher prices.
- Certain makes and models have a significant positive impact on vehicle prices.
- Vehicles with more cylinders, often indicating better performance, typically fetch higher prices.
- Better vehicle condition usually translates to higher resale value.
- Higher mileage significantly lowers the vehicle price.
- Clear title statuses increase vehicle value.
- Older vehicles see a significant decrease in value with age.

#### Strategic Recommendations

- **Refine Pricing Tactics:**  
  Utilize dynamic pricing models that factor in mileage, vehicle age, and market demand to optimize profit margins. Stay attuned to regional market trends, adjusting prices to reflect local conditions and demand.

- **Enhance Inventory Management:**  
  Prioritize stocking high-demand vehicles and brands known for strong resale values. Leverage predictive analytics to forecast sales velocity and optimize inventory turnover, ensuring efficient stock management.

- **Boost Customer Engagement:**  
  Focus marketing efforts on key selling points such as low mileage and in-demand models. Strengthen customer trust by offering transparent pricing structures and providing comprehensive vehicle history reports.

- **Continuously Improve the Predictive Model:**  
  Regularly refresh the predictive models with updated data to ensure ongoing accuracy. Integrate customer feedback and evolving market insights to fine-tune the model's performance.

By applying these strategies, the business can strengthen its competitive position, drive revenue growth, and enhance customer satisfaction.

## Future Work
- **Dynamic Pricing Models:** Develop a dynamic pricing system that can adjust prices based on inventory, demand, or regional economic conditions in real-time.
- **Customer Personalization:** Use model outputs to offer personalized pricing or promotions to customers based on their browsing or purchasing behavior.

## Repository Structure
- <code>data/vehicles.csv</code>: Contains dataset used in the analysis.
- <code>notebooks/used_car_predictive_pricing.ipynb</code>: Jupyter notebook with code.
- <code>README.md</code>: Summary of findings and link to notebook

## Notebook
The detailed analysis and code can be found in the Jupyter notebook <a href="https://github.com/NRUTHVIIK1396/Predictive-pricing-for-used-cars/blob/main/notebooks/used_car_predictive_pricing.ipynb">here</a>.