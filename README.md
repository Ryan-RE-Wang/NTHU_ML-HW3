# NTHU_ML-HW3

In this assignment we are going to build a machine learning model to predict the 30-day mortality of patients using chest X-ray images (CXR).

That is, whether a patient will die in the hospital within 30 days.

There are 1393 patients in the training dataset and each with a CXR JPG image. Each image has been processed with histogram equalization.

This assignment also has bonus part, which is to combine EHR data provided in assignment2 with CXR to enhance model performance.

In this assignment, I implement transfer learning technique since train data is too few to train. I use a DenseNet121 based model pretrained on MIMIC-CXR dataset in MIMIC-Racial-Fairness project to train on these 1393 CXR images. 

For bonus part, I implement 2 methods to combine CXR and EHR.
1. I trained a multi layer perceptron (MLP) model and set two inputs for the model, one for CXR another for EHR.

2. I freeze the pretrained model and get the features of CXR of last CNN layer of pretrained model. I combined the features of CXR with EHR, and train several models, such as MLP, XGboost, LogisticRegression, AdaBoostClassifier, DecisionTreeClassifier, RandomForestClassifier, KNeighborsClassifier, GradientBoostingClassifier, stcking classifier, hard voting classifier, and soft voting classifier. I combined the result of these models by averaging them to get final result.   
