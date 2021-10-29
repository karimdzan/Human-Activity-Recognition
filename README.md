# Human-Activity-Recognition

This project was part of the course on Human Activity Recognition where the students were requested to gather the data by 5 samples of 6 different activities, such as: walking, jogging, standing, on car, going up and down the stairs, cycling. The data gathered then had to be collected in Training and Testing samples.

Data processing was to use padding in order to first parse the names of the files, and to put a target variable based on the activity. The data consisted of g-force meters report of the xyz position of the subject, which then i split into window time frames of the size 128 points in order to squeeze the data and optimize the training, as this size of the window turned out to be optimal in my case. Then before feature engineering step it was important to separate the validation set from the training data.

After preprocessing I constructed 90 statistical features(mean, max, stddev) and additional 30 features of the fourier transform of some general features. After that i used StandardScaler in order to scale all the features to the same range.

I used to experiment on different classifiers such as CatBoostClassifier and classical XGBoost, but in the end, the optimal result on the trainig and validation sets was reached using RandomForestClassifier(94% on training data and 87% on test data).
