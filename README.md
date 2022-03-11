# WiDS_Datathon_ClimateChange

WiDS Datathon 2022 - https://www.kaggle.com/c/widsdatathon2022/overview

This challenge aims at analyzing differences in building energy efficiency, creating models to predict building energy consumption. We use a dataset consisting of variables that describe building characteristics and climate and weather variables for the regions in which the buildings are located. The WiDS Datathon dataset was created in collaboration with Climate Change AI (CCAI) and Lawrence Berkeley National Laboratory (Berkeley Lab).

## Objectives
Buildings accounted for 37% of global greenhouse gas emissions in 2020 ([IEA 2020](https://www.iea.org/reports/tracking-buildings-2021)). “Green building” is key to achieving the Paris Agreement goal. Policymakers and urban planners around the world employ various policy tools, such as building codes or financial incentives programs to retrofit, to improve the energy efficiency of buildings and construction sectors. For the program’s effective intervention, detailed data of energy consumption for each building is necessary. For example, many states in the U.S. mandate building energy disclosure, yet, it is still far from covering all buildings in the U.S. 

To fill this gap of building energy consumption data availability, we developed a prediction model of building energy consumption using data from the U.S., including building characteristics and climate and weather variables for the building's location. Our model provides granular energy usage predictions for each building. In addition, our prediction can support policymakers and urban planners in the U.S. to identify and prioritize a building in order to intervene and design necessary retrofitting programs without detailed building energy consumption data.

The model was submitted to a [Kaggle competition](https://www.kaggle.com/c/widsdatathon2022/overview/description) that WiDS Datathon 2022 hosts. 

## Data
The data set is provided through a Kaggle competition. Our target variable is the annual energy usage per square foot of a building, called **the site energy usage intensity (EUI)**. Our features include **building characteristics** (e.g., floor area, years of built, facility type) and **weather data for the building’s location** (e.g., annual average temperature, annual total precipitation, annual snowfalls). We received the training set with the target variable and the test set without the target variable. The test set is used for submission to the Kaggle competition. The training data has 75,757 observations covering 6 years from 7 states. The years and states are anonymized. 

The detailed list of features in our model is [here](https://www.kaggle.com/c/widsdatathon2022/data). 

For data cleaning and EDA, please read our notebooks.
- [Data Cleaning Notebook](https://github.com/eminaomasa/energy_usage_prediction/blob/main/DataCleaning.ipynb)
- [EDA Notebook](https://github.com/eminaomasa/energy_usage_prediction/blob/main/EDA.ipynb)

## Modeling
Considering this is the regression model, we evaluated 8 machine learning algorithms to predict EUI. We used `Root mean Square Error` scores to select the final model. 


1.	Decision Tree 
2.	Random Forest
3.	Gradient Boosting (GBM)
4.	Light Gradient Boosting (Light GBM)
5.	Extreme Gradient Boosting (XGBM)
6.	Catboost 
7.	Adaboost
8.	Neural Network (Multi layer Perceptron)

To reduce the parameter tuning time, we first checked each model’s `Root Mean Square Error` score in a default setting, and then for the top-performing models, we did hyperparameter tuning with a random search. Finally, we used a voting regressor on a combination of four best models (XGBoost, CatBoost, LightGBM and MLP) as our final model.

For modeling, please read our notebooks.
- [Model Notebook](https://github.com/sneha012/WiDS_Datathon_ClimateChange/blob/main/model.ipynb)

For EDA, please check [here](https://github.com/sneha012/WiDS_Datathon_ClimateChange/blob/main/EDA.ipynb)


## Results

Our team secured 16th position on the final leaderboard with a final score of 19.425 (https://www.kaggle.com/c/widsdatathon2022/leaderboard)

**Team members :**

1) Sneha Jhaveri

2) Navya Dahiya

3) Rohit Rawat

4) Gautham Pughazhendi

## Repository Structure

```
├── data                                            <- Data downloaded from the kaggle competition
├── model.ipynb                                     <- Solution notebook
├── EDA.ipynb                                       <- EDA Notebook
├── submission_SJ.csv                               <- Sample submission file generated from model.ipynb
└── README.md                                       <- README file                                           
                           
```  

