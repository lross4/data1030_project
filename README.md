## Predicting Kidney Transplant Allocation in Brazil with ML
#### Lindsey Ross 
#### Brown University  |  DATA 1030  |  Professor Zsom

Data source: [Brazil Kidney Waitlist](https://www.kaggle.com/datasets/gustavomodelli/waitlist-kidney-brazil) retrieved from a public repository on Kaggle.

#### Introduction
The goal of this project is to create a machine learning model that is capable of predicting whether or not a new patient added to a kidney transplant waitlist will receive a kidney from a deceased donor. This is a binary classification problem. The target variable is a categorical variable called `Transplant_Y_N`, and it contains 2 classes — ‘Y’ indicates that the patient received a kidney transplant and ‘N’ indicates that the patient did not receive a kidney transplant. 

#### Methods
The intended use of this model would be to predict whether or not a new patient added to the SP-OAS waitlist will receive a kidney transplant. Utilizing SciKit-Learn’s powerful library of ML tools, a pipeline was developed that splits and preprocesses input data, then trains a ML model and performs cross-validation and hyperparameter tuning. The pipeline is performed 5 times for each unique ML algorithm using 5 different random states. The pipeline returns the best models, test scores, and baseline scores for each random state for each ML algorithm.  

Logistic regression, linear support vector classification (SVC), random forest, and XGBoost classification were used. K-fold cross validation and hyperparameter tuning using GridSearchCV were performed. 

Accuracy scores were used to evaluate each model’s performance because they are easily interpretable for classification problems. F-beta scores with beta=0.5 were also calculated. Uncertainties due to splitting and/or non-deterministic ML methods were measured by calculating the standard deviations of the test scores for each model that were found across all 5 random states tested. Global and local feature importances were calculated and visualized.

#### Organization
- `data/` contains the raw data downloaded from Kaggle, as well as three csv files which contain the preprocessed training, validation, and test datasets. Descriptions of each feature in the raw data can be found here as well.
- `figures/` contains all figures produced by the code in the project.
- `results/` contains the best models developed, as well as the best test sets, test scores, and baseline scores. A combined test set with predictions for each patient based off of the best model can be found here as well.
- `report/` contains a pdf version of a detailed final report on this study.
- `src/` contains the source code, an ipython notebook.
- `LICENSE`

#### Python versions and packages used
Python versions and the packages required for this code can be found in the `data_environment.yml` file. A shorter list of dependencies is included below:
- python=3.10.5
- matplotlib=3.5.2
- pandas=1.4.2
- scikit-learn=1.1.1
- numpy=1.22.4
- xgboost=1.5.1
- shap=0.40.0
- jupyter_client=7.3.1
- jupyter_core=4.10.0
- jupyterlab=3.4.2
- jupyter_server=1.17.0
- jupytext=1.13.8
- rise=5.7.1
- plotly=5.8.0
- ipywidgets=7.7.0

