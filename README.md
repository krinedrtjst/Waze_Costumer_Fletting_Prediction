# Waze_Costumer_Fletting_Prediction
### **Sharing the Findings**

> _ This project successfully developed and evaluated machine learning models to predict user churn at Waze. The initial baseline model, XGBoost, provided a solid performance benchmark, while a more advanced LSTM neural network, optimized through an automated framework, demonstrated a significant potential for breakthrough performance.

> _ Baseline Model Performance and Trade-offs
The initial modeling phase focused on tree-based ensembles like Random Forest and XGBoost. These models were chosen because they generally offer superior predictive performance compared to simpler, more interpretable models like logistic regression. The champion baseline model, XGBoost, established a performance benchmark with a recall of approximately 18.1% on the test set. While functional, this level of recall was deemed insufficient for making high-stakes business decisions, suggesting its best use would be for guiding exploratory analysis.

> _ Advanced Modeling with LSTMs and Automated Optimization
To improve upon the baseline and capture potential time-based patterns in user behavior, a more advanced Long Short-Term Memory (LSTM) neural network was implemented. Recognizing that such complex models have numerous hyperparameters that are difficult to tune manually, we employed an automated optimization framework, Optuna, to systematically find the best model configuration. This process efficiently evaluated various model architectures and utilized an intelligent pruning strategy, automatically stopping unpromising trials early to save computational resources.

> _ Key Result: A Breakthrough in Predictive Power
The automated search discovered an LSTM model configuration that achieved a validation recall of 97.8%. This represents a potential 440% improvement over the XGBoost baseline's recall score, demonstrating the profound impact of using a sequential model with optimized hyperparameters for predicting user churn. This result directly challenges the initial conclusion; a model with such high recall is a strong candidate for being integrated into business operations to proactively reduce churn.

> _ Recommendations for Model Enhancement
To further enhance this model, future work should focus on two key areas. Firstly, feature engineering, which was highly effective in this project, could be expanded with more domain knowledge to create better predictive signals. Secondly, the model could be significantly improved by incorporating more granular data, such as drive-level information (times, locations), user interaction data (e.g., hazard reporting frequency), and unique start/end location counts.

> _ Methodological Note
The project's robust methodology involved splitting the data into training, validation, and test sets. This ensures that the final performance metrics, gathered from the unseen test set, are a reliable estimate of how the model would perform on new, real-world data.

> _The recommendentions on the model will depends on the intended use of the model. If the model is meant to inform significant business decisions, then no, it is not reliable enough due to its poor recall score. However, if the model is intended to guide further exploratory analysis, it could still be valuable.._

> _Splitting the data into training, validation, and test sets results in the data into three sets results in less data available for training the model compared to a two-way split. However, using a separate validation set for model selection allows for testing the champion model solely on the test set, providing a more accurate estimate of future performance than splitting the data two ways and choosing the champion model based on test data performance.._

> _The advantage of using a logistic regression model instead of an ensemble of tree-based models  for classification tasks lies in its interpretability. Logistic regression models are easier to understand because they assign coefficients to predictor variables. This not only shows which features are most influential in the final predictions but also indicates whether each feature is positively or negatively correlated with the target variable._

> _The advantage of using an ensemble of tree-based models like random forest or XGBoost over a logistic regression model for classification tasks is that tree-based model ensembles often provide better predictive performance. If the primary goal is to maximize the model's predictive power, tree-based models typically outperform logistic regression (though not always!). Additionally, they require less data cleaning and make fewer assumptions about the distributions of predictor variables, making them easier to work with.._

> _To enhance this model, new features could be engineered to provide better predictive signals, especially if domain knowledge is applied. For this model, engineered features accounted for over half of the top 10 most predictive features. Additionally, reconstructing the model with different combinations of predictor variables could help reduce noise from less predictive features.._

> _It would be an additional helpful feature to have drive-level information for each user (such as drive times, geographic locations, etc.) for improve the model. It would probably also be helpful to have more granular data to know how users interact with the app. For example, how often do they report or confirm road hazard alerts? Finally, it could be helpful to know the monthly count of unique starting and ending locations each driver inputs._

