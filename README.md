# Smart Grid Stability Prediction Using Machine Learning

This project leverages machine learning to predict smart grid stability amidst the complexities introduced by renewable energy sources. Traditional models, like Decentral Smart Grid Control (DSGC), struggle to accurately capture dynamic behaviors, highlighting the need for advanced predictive solutions.

## Dataset

Utilizing the **Electrical Grid Stability Simulated Dataset** from Kaggle, the project simulates a 4-node star network consisting of one energy supplier and three consumers. The dataset features **12 predictive variables** related to grid dynamics and includes a binary label indicating stability (Stable/Unstable).

### Dataset Description
This project uses the "Electrical Grid Stability Simulated Dataset," which simulates a 4-node star network comprising one energy supplier and three consumers. The dataset consists of 60,000 observations after augmentation (originally 10,000). Each observation contains 12 predictive features related to the grid's dynamic behavior and two dependent variables, including a binary label for grid stability (stable or unstable).

### Feature Description
* **Reaction times (τ1 to τ4):** Represent the response times of each network participant to changes in energy pricing.
* **Nominal power produced or consumed (p1 to p4):** Measure energy production (positive values) and consumption (negative values). The balance between total energy produced and consumed is critical for stability.
* **Price elasticity coefficients (g1 to g4):** Reflect how participants' energy consumption or production behavior changes in response to price fluctuations.

The dependent variable 'stabf' is a binary label representing grid stability (1 = stable, 0 = unstable). This label will be the target for the classification models.

## Workflow

1. **Data Acquisition:** Downloaded the dataset from Kaggle.
2. **Exploratory Data Analysis (EDA):**
   * Analyzed feature distributions and correlations to assess their impact on stability.
3. **Data Preprocessing:**
   * Normalized and managed categorical variables, splitting data into training, validation, and test sets.
4. **Model Training and Evaluation:**
   * Implemented and compared multiple models:
      * **Logistic Regression**
      * **Naive Bayes**
      * **Support Vector Machine (SVM)**
      * **Random Forest**
      * **XGBoost**
      * **Deep Neural Network**
5. **Hyperparameter Tuning:** Used RandomizedSearchCV for optimal performance in Random Forest and XGBoost.
6. **Model Comparison:** Evaluated models on accuracy, precision, recall, F1-score, and confusion matrices.

## Results and Model Performance

| Model | Accuracy (%) | Precision (Class 0) | Recall (Class 0) | F1-Score (Class 0) | Precision (Class 1) | Recall (Class 1) | F1-Score (Class 1) | Confusion Matrix |
|-------|--------------|---------------------|------------------|--------------------|--------------------|------------------|--------------------|------------------|
| Logistic Regression | 82.25 | 0.844 | 0.884 | 0.864 | 0.779 | 0.716 | 0.746 | [[6743, 887], [1243, 3127]] |
| Naive Bayes | 84.08 | 0.837 | 0.932 | 0.882 | 0.851 | 0.682 | 0.757 | [[7108, 522], [1388, 2982]] |
| SVM | 97.83 | 0.980 | 0.986 | 0.983 | 0.976 | 0.965 | 0.970 | [[7525, 105], [155, 4215]] |
| Random Forest | 95.81 | 0.961 | 0.974 | 0.967 | 0.953 | 0.931 | 0.942 | [[7430, 200], [303, 4067]] |
| **XGBoost** | **99.06** | **0.992** | **0.994** | **0.993** | **0.989** | **0.985** | **0.987** | **[[7581, 49], [64, 4306]]** |
| Deep Neural Network | 98.24 | 0.985 | 0.988 | 0.986 | 0.978 | 0.973 | 0.976 | [[7535, 95], [116, 4254]] |

## Key Takeaways:

* **XGBoost** excelled with **99.06% accuracy**, showcasing exceptional precision and recall, making it ideal for complex grid stability predictions.
* The **Deep Neural Network** and **SVM** also demonstrated high accuracy, providing reliable alternatives.
* Simpler models like **Logistic Regression** and **Naive Bayes**, while effective, did not match the advanced algorithms in performance.

## Conclusion

This project underscores the power of machine learning, especially XGBoost, in enhancing smart grid stability predictions. Accurate forecasting can significantly aid grid operators, improving energy distribution and resilience in renewable-heavy systems.


## Next Steps:
Create an interactive dashboard using Streamlit to visualize the model predictions, comparison metrics, and provide an engaging way for audience to explore the results.
