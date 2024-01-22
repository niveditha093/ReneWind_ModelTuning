# ReneWind_ModelTuning

### Business Context

Renewable energy sources play an increasingly important role in the global energy mix, as the effort to reduce the environmental impact of energy production increases.

Out of all the renewable energy alternatives, wind energy is one of the most developed technologies worldwide. The U.S Department of Energy has put together a guide to achieving operational efficiency using predictive maintenance practices.

Predictive maintenance uses sensor information and analysis methods to measure and predict degradation and future component capability. The idea behind predictive maintenance is that failure patterns are predictable and if component failure can be predicted accurately and the component is replaced before it fails, the costs of operation and maintenance will be much lower.

The sensors fitted across different machines involved in the process of energy generation collect data related to various environmental factors (temperature, humidity, wind speed, etc.) and additional features related to various parts of the wind turbine (gearbox, tower, blades, break, etc.).



## Objective
“ReneWind” is a company working on improving the machinery/processes involved in the production of wind energy using machine learning and has collected data of generator failure of wind turbines using sensors. They have shared a ciphered version of the data, as the data collected through sensors is confidential (the type of data collected varies with companies). Data has 40 predictors, 20000 observations in the training set and 5000 in the test set.

The objective is to build various classification models, tune them, and find the best one that will help identify failures so that the generators could be repaired before failing/breaking to reduce the overall maintenance cost.
The nature of predictions made by the classification model will translate as follows:

- True positives (TP) are failures correctly predicted by the model. These will result in repairing costs.
- False negatives (FN) are real failures where there is no detection by the model. These will result in replacement costs.
- False positives (FP) are detections where there is no failure. These will result in inspection costs.

It is given that the cost of repairing a generator is much less than the cost of replacing it, and the cost of inspection is less than the cost of repair.

“1” in the target variables should be considered as “failure” and “0” represents “No failure”.

## Data Description
- The data provided is a transformed version of original data which was collected using sensors.
- Train.csv - To be used for training and tuning of models.
- Test.csv - To be used only for testing the performance of the final best model.
- Both the datasets consist of 40 predictor variables and 1 target variable


* **Focus on High-Impact Features:** Prioritize monitoring and maintenance efforts on the top 5 features identified by the XGBoost model (V36, V16, V26, V14, V18). These variables have shown the strongest influence on predicting potential failures and should be closely monitored for any deviations.

* **Enhance Proactive Maintenance in Critical Areas:** Concentrate proactive maintenance activities on instances flagged as True Positives by the model. By addressing potential failures before they occur, the organization can minimize downtime, reduce repair costs, and ensure the reliability of wind energy systems.

* **Optimize Inspection Strategies:** Refine inspection procedures for areas highlighted by the model as potential failure points. This optimization will help streamline inspection efforts, minimizing false positive detections and associated inspection costs.

* **Continuous Model Monitoring and Retraining:** Implement a system for continuous monitoring of the model's performance. Periodically retrain the model using updated data to ensure its effectiveness remains consistent over time, considering the dynamic nature of wind energy systems.

* **Cross-Functional Collaboration:** Encourage collaboration between data science teams and maintenance personnel. The insights generated by the model should be shared and discussed with those on the ground, fostering a collaborative approach to predictive maintenance.


The test score for the XGBoost model tuned with oversampled data using Random Search is as follows:

- **Accuracy:** 97.9%
- **Recall:** 84.8%
- **Precision:** 79.1%
- **F1 Score:** 81.8%

This indicates that the model maintains strong performance on previously unseen data, showcasing its effectiveness in identifying potential failures while minimizing false negatives and maintaining a good balance between precision and recall.
