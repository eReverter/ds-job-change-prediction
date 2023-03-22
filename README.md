# Binary Model Creation to Predict Job Change

This project creates a binary model to predict whether a candidate will work for a company or change jobs. The dataset is cleaned, explored, and modeled to assess the best variables to work with and improve the model's predictive power. The final model predicts with decent accuracy and balanced accuracy. Everything was computed through R.

The following is a brief summary of each section of the report, which may appear messy due to the need for knitting. For more details, see the [pdf](reports/main.pdf).

## TOC
- [Problem Statement](#problem-statement)
- [Data Collection and Cleaning](#data-collection-and-cleaning)
- [EDA](#eda)
- [Modeling](#modeling)
- [Conclusion](#conclusion)

## Problem Statement

The problem statement for this project is to create a binary model that can predict whether a candidate will work for a company or change jobs. The dataset provided includes information on demographics, education, experience, and other factors that may influence a candidate's decision. The goal is to use this data to predict the probability of a candidate looking for a new job or staying with the company, as well as interpreting the factors that affect the candidate's decision. Data preparation, profiling, and feature selection, modeling, residual analysis, and goodness of fit will be utilized to achieve this goal. Additionally, missing imputation is required, and the dataset is imbalanced, with most features being categorical. The assessment metric will be the area under the ROC curve score and confusion table prediction capability analysis for train and test samples.

## Data Collection and Cleaning

The dataset contains a lot of missing values, which might condition the imputation methods. The missing values are imputed using logic and algorithms. A set of observations with more than 50% missing values is deleted. After the logical imputation, the remaining missing values are imputed using factorial analysis for mixed data. Outliers are not detected in the two numerical variables, and the training_hours variable is not too extreme, so imputation is not done in this case.

## EDA

The categorical variables with which the modeling is done are visualized to gain insights. The response variable is significantly associated with all the numerical and categorical variables except for training_hours. People who want to change jobs tend to be from less developed cities with no data regarding the company, have less experience, and higher education. The data is split into working and test datasets to limit overfitting.

## Modeling

The data is modeled by assessing the best way to treat variables, such as experience as a factor or numerical variable. Polynomial transformations are applied to the numerical variable experience, and it is seen that the second order polynomial is kept. The categorical variable experience is collapsed by quantiles. The best type of variables to work with is chosen, and the additive effect of variables is explored. Some factors still have a lot of levels, but two of them can be further collapsed to improve the model results. The model resulting from the bic step is studied, and its coefficients are interpreted. Outliers are detected with the Cook's distance method and removed, and the model is reevaluated. The ROC curve and confusion matrix are assessed on the test set.

## Conclusion

The project highlights the importance of initial data treatment, which affects the final outcome of the model. The modeling process includes variable treatment, transformation, addition, and interaction, and the residuals and influential observations are addressed. The model's predictive power is assessed using ROC curves, confusion matrices, and Hoslem tests. Overall, the model predicts whether a candidate will work for a company or change jobs with decent accuracy (0.767) and balanced accuracy (0.683).
