<h1 align="center">DSAI-Project</h1>
<h4 align="center" >Analyzing financial metrics to predict bankruptcy</h4>

<h1>Overview</h1>

This is a Mini-Project for SC1015 (Introduction to Data Science and Artificial Intelligence) which focuses on a [bankruptcy dataset](https://github.com/paaniwater/DSAI-Project/blob/main/bankruptcy.csv) obtained from kaggle, obtained from the Taiwan Economic Journal (1999–2009). 

<h1>Video Presentation</h1>

The video presentation can be found [here](https://youtu.be/so_m5sz5qFo).

<h1>Presentation Slides</h1>

The slides can be found [here](https://github.com/paaniwater/DSAI-Project/blob/main/DSAI_Presentation_BankruptcyAnalysis.pdf).

<h1>The Problem</h1>

### Background
Since 2000, 745,566 Businesses have filed for Bankruptcy in the US. **Bankruptcy can result in significant financial losses** for entities, and being able to predict bankruptcy can help entities pinpoint their problems and cut their losses. 
However, the abundance of financial data can pose a challenge in determining which factors to prioritize when forecasting the likelihood of a company's bankruptcy

### Problem Definition
Therefore, we aim to answer the question of:

**What is the optimum Machine Learning model to predict the likelihood of a company going Bankrupt and are there specific variables that can better determine Bankruptcy?**


<h1>Code Walkthrough</h1>

Detailed explanation of code can be found in each individual notebook.

### 1. Data Cleaning and Exploratory Data Analysis / Visualisation
In the [data_visualisations.ipynb](https://github.com/paaniwater/DSAI-Project/blob/main/data_visualisations.ipynb) notebook, we performed the following to ensure our dataset is cleaned, and to better understand our dataset:

1. Data Cleaning
2. Analytic Visualisation
3. Evaluating Outliers

We then concluded that it was necessary to upsample our dataset before using it to train our machine learning models as our dataset was highly imbalanced, and would have given us bias results. 

### 2. Data Preparation
We then performed upsampling of our data in [data_upsampling.ipynb](https://github.com/paaniwater/DSAI-Project/blob/main/data_upsampling.ipynb). In here, we generated the dataset [upsampled_bankruptcy.csv](https://github.com/paaniwater/DSAI-Project/blob/main/upsampled_bankruptcy.csv) to use for our machine learning models. 

### 3. Use of Machine Learning
After cleaning, understanding and prepping our data, we then used 3 machine learning models to predict bankruptcy and compared the performance of the 3.

Models used:
1. Neural Network Model

    [neural_network.ipynb](https://github.com/paaniwater/DSAI-Project/blob/main/neural_network.ipynb)
2. Decision Tree Model

    [decision_tree.ipynb](https://github.com/paaniwater/DSAI-Project/blob/main/decision_tree.ipynb)
3. Support Vector Machines

    [svm.ipynb](https://github.com/paaniwater/DSAI-Project/blob/main/svm.ipynb)

For each type of machine learning model used, we trained 2 models, one with the full dataset (all 95 variables), and one with the top 10 variables. This is so as to ascertain whether it would be plausible to predict bankruptcy with just the top correlated variables, which would be more efficient than using 96 variables.

### 4. Evaluation and Final Insights
Last but not least, we compared the performance of all 6 models in [model_comparison.ipynb](https://github.com/paaniwater/DSAI-Project/blob/main/model_comparison.ipynb), using 2 primary metrics:

1. Area Under Curve (AUC) of the Receiver Operating Characteristic (ROC) Graph
2. Accuracy of model obtained from the Classification Report of each model

We then concluded that the **Neural Network model is the best machine learning model for predicting bankruptcy**, and that models trained using the full dataset performed better than those trained with only the top 10 variables.

<h1>Discussion and Conclusion</h1>

Based on the results that the models trained using the full dataset performed better than those trained with only the top 10 variables, we can infer that **factors affecting bankruptcy are not mainly limited to the top 10 correlated variables**. Rather, entities would have to consider all aspects of a business to ascertain the factors potentially leading to the predicted bankruptcy of a company.

Additionally, while we have concluded that the Neural Network model is the best amongst the 3 in predicting bankruptcy, this conclusion can vary depending on the context used. 

Based on our findings, the top 2 models is the Neural Network model, with the highest AUC, and the Decision Tree, with the highest accuracy. Therefore, the Neural Network model should be used in situations where the cost of false negatives (classifying a bankrupt firm as non-bankrupt) is likely to be much higher than the cost of false positives (classifying a non-bankrupt firm as bankrupt). 

Thus, stakeholders have to properly weigh the costs of false negatives and false positives in the context of their decision making before deciding whether to use the predictions made by the Neural Network model, or by the Decision Tree Model.

<h1>Our Learning Points</h1>
In this project, we utilised technologies and skills that were not covered in the course module so as to ensure proper evaluation of our dataset, which included:

- Upsampling of data

- Using Neural Network Models for data classification and prediction

- Using Support Vector Machines for data classification and prediction

- Utilising Receiver Operating Characteristic (ROC) and its Area Under Curve (AUC) to compare and evaluate performance of machine learning models

### Tech Stack

<div align="center">
  <a href="https://keras.io/img/logo.png">
    <kbd>
      <img src="https://keras.io/img/logo.png" height="60" />
    </kbd>
  </a>
  <a href="https://user-images.githubusercontent.com/315810/92255284-156f1180-eea0-11ea-9d2d-be8262670e8c.png">
    <kbd>
      <img src="https://user-images.githubusercontent.com/315810/92255284-156f1180-eea0-11ea-9d2d-be8262670e8c.png" height="60" />
    </kbd>
  </a>
  <a href="https://upload.wikimedia.org/wikipedia/commons/thumb/e/ed/Pandas_logo.svg/2560px-Pandas_logo.svg.png">
    <kbd>
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/ed/Pandas_logo.svg/2560px-Pandas_logo.svg.png" height="60" />
    </kbd>
  </a>
  <a href="https://upload.wikimedia.org/wikipedia/commons/thumb/0/05/Scikit_learn_logo_small.svg/1200px-Scikit_learn_logo_small.svg.png">
    <kbd>
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/05/Scikit_learn_logo_small.svg/1200px-Scikit_learn_logo_small.svg.png" height="60" />
    </kbd>
  </a>
  
  <br />
  <h4>Keras | seaborn | pandas | scikitlearn</h4>
</div>
<br />

<h1>Contributors</h1>

- Nathaniel Yew (@nathanielyew)
- Ong Jing Xuan (@ongjx16)
- Somesh Sahu (@paaniwater)

<h1>References</h1>

1. US Courts. (January 1, 2023). Annual number of business bankruptcy cases filed in the United States from 2000 to 2022 [Graph]. In Statista. Retrieved April 21, 2023, from https://www.statista.com/statistics/817918/number-of-business-bankruptcies-in-the-united-states/
2. Bhandari, A. (2023). Guide to AUC ROC Curve in Machine Learning : What Is Specificity? Analytics Vidhya. https://www.analyticsvidhya.com/blog/2020/06/auc-roc-curve-machine-learning/#What_is_the_AUC-ROC_Curve?
3. Krawczyk, B. (2016). Learning from imbalanced data: open challenges and future directions. Progress in Artificial Intelligence, 5(4), 221–232. https://doi.org/10.1007/s13748-016-0094-0
