# Cardiovascular disease diagnosis

For the Dartmouth class COSC 89.20, Data Science for Health. Project members are Srishti Bagchi, Rachael Chacko, and Cara Van Uden. The completed manuscript detailing this project is included here (in this repository.)

## Overview

Cardiovascular disease (CVD) is a term for any type of pathology of the heart which results in inefficient circulation of blood. CVD is responsible for 31% of deaths, worldwide, but 200,000 of deaths could be avoided in just the United States through early diagnosis of CVD. However, current CVD diagnostic procedures are invasive, costly, and requires a clinical setting. Previous studies have generated models to predict CVD based off of this more detailed examination data (e.g. ECG, fluoroscopy, myocardial scintigraphy.) While these tests can provide detailed data, they can often be expensive to both patients and healthcare facilities and may not always be useful toward the diagnostic process. If we can demonstrate that our model can achieve a similar level of accuracy with data that can be obtained more quickly and easily than that from the typical medical exam (especially if this information could be instantaneously gathered via a mobile health device such as a FitBit), then this technology could streamline the diagnostic process and bring medicine to the home. In this project, we attempted to apply machine learning models on two datasets: one containing invasive data that would be collected in a clinic, and another containing non-invasive data that could be collected via survey or commercial activity-tracker. By comparing the performance of predictive models on these two datasets, we may be able to state whether reliable CVD diagnosis is attainable with non-invasive data (that could be collected via activity monitor) or if invasive data is indeed required.

## Methodology

1. Preprocessing and cleaning the dataset. There were several outliers in the non-invasive dataset in which values for BP were abnormally high. Those outlier datapoints were removed, bringing the size of the dataset down from 70,000 to 67,007. All variables were then normalized to remove potential biases.
2. Detecting the presence or absence of CVD { a binary classification problem. As there exist many machine learning algorithms capable of accurate binary classification, we decided to implement various models and evaluate their performance (as measured by accuracy, precision, recall, and F1 score). Therefore, we chose to utilize several commonly used models, including GNB, SVM, k-NN, LR, and RF. These models implement widely different model architectures between one another, yet all are also known for their reliability and generalizability. We also implemented a MLP to explore whether a deep learning approach could result in a more successful model. 
3. Comparing the performance of machine learning models trained on the non-invasive dataset versus the more invasive UCI dataset. This involved comparing performance (as measured by accuracy, precision, recall, and F1 score) of logistic regression models for CVD diagnosis after training on each dataset. We used LR for this comparison due to the promising performance of LR on the non-invasive dataset and because LR models have easily-interpretable feature importances. Feature coefficients can range between -1 (strongly pushes classification towards the negative class) and 1 (strongly pushes classification towards the positive class).
4. Predicting other target variables. We used regression models to predict BP and body mass index (BMI). We mention the performances of these models briefly in this study but do not elaborate on them because none of the regression models demonstrated any notable performance, and because BP and BMI are already simple to measure.

## Dataset

Our non-invasive dataset is an open-source Kaggle dataset, although information on how the data was collected and by whom was lacking. The dataset has health information and information on the presence/absence of CVD for 70,000 patients (34,979 presenting with CVD and 35,021 not presenting with CVD). The dataset has 11 features. It can be found [here](https://www.kaggle.com/sulianova/cardiovascular-disease-dataset).

Our invasive dataset is the open-source UCI CVD dataset. It is a much smaller dataset than our non-invasive dataset, with only 303 samples. Though it does not include behavioral data like our non-invasive dataset, it includes some features that either take more time or are more invasive to obtain, such as fluoroscopy, ECG, and exercise-induced angina. Features of the dataset are either continuous, assigned categorical codes, or are binary. The dataset can be found [here](https://www.google.com/url?q=https%3A%2F%2Fwww.kaggle.com%2Fronitf%2Fheart-disease-uci&sa=D&sntz=1&usg=AFQjCNEEjqV9dwSgVx5ipw5Omt8rVR1RiA).

## Results

The highest accuracy obtained from training and testing on the non-invasive dataset was 60% from logistic regression. From training and testing on the invasive dataset, a logistic regression was able to achieve 87% accuracy. This suggests that invasive data may be necessary for an accurate CVD diagnosis. Future work may include using different types of non-invasive data that, hopefully, would be able to properly train a predictive model.
