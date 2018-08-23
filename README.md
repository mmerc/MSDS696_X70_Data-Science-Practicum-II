# Predicting Chronic Kidney Disease with Machine Learning Techniques.
Chronic Kidney Disease (CKD) is the loss of kidney function over a long period of time. The kidneys filter waste chemicals from the blood, secrete hormones that alter blood pressure and red blood cell production, and they regulate electrolytes. This disease affects 30 million individuals in the United States and is most often caused by diabetes and high blood pressure (NKF, 2017).

This paper describes the process to predict the presence of Chronic Kidney Disease using machine learning techniques. The models utilized for this project are the random forest classifier and support vector machine (SVM) contained in the sklearn package. The process for this project includes exploratory data analysis, data cleansing, establishing a training and test sample, application of the machine learning model and evaluating the performance of each model.

### Dataset
The dataset is the "Chronic_Kidney_Disease Data Set" from the UCI Machine Learning Repository (UCI, 2015). The data consisted of 400 samples of patient data on 24 features related to chronic kidney disease. The 25th feature was the dependent variable on whether the patient had chronic kidney disease. Another aspect of this project was to compare the performance of each model on variations of the dataset. I was interested in learning if fewer samples with more features yielded different results as compared to more samples with fewer features.

### Exploratory Data Analysis
The features included in this data set are the common tests used to diagnose kidney disease such as urine characteristics, and blood tests, as well as medical history and a few physical findings. As the kidney function declines through progressive cellular damage, alterations in the composition of the urine, the blood chemistries, and physical features occur.

A detailed description of each feature is listed in the Jupyter notebook.  The average age for this dataset was 51.5 years of age with a mode of 60 years.  Overall, a majority of the patients had normal urine results. Most of the samples had elevated serum urea and creatinine levels which are the hallmark tests for kidney disease.  Furthermore, a majority of the individuals did not have diabetes, hypertension or coronary heart disease.

### Data Cleansing
All nominal features were changed to numeric binary numbers of zero or one.  The dependent variable was changed to binary data where zero represents no CKD, and one represents that the patient had CKD.

The first data frame designed for the machine learning models consisted of remove all rows with NaNs.  This left 158 rows out of 400 rows and included all features.  Also, two erroneous potassium values were corrected, and nonnumerical characters were removed from other features.  This data frame is labeled df2. 

The second data frame designed for this project consisted of including more rows with fewer features.   I used the technique to drop the columns with greater than 15% NaNs as described by Aqlan, Markle, and Shamsan (2017). However, I chose to impute the remaining missing values with the mode since most of the remaining features were categorical.  This data frame is labeled df3.

### Prediction Models
The prediction models utilized in this project are random forest and support vector machine from the sklearn package.  Both models were applied to both df2 and df3 data frames.  The cross-validation process was applied to each model to validate its performance.

### Results
The random forest classification model on both data sets yielded 100% accuracy for precision, recall, the f1 score for an overall accuracy score of 100%, which is similar to the results achieved by Aqlan, Markle, and Shamsan (2017), although their data set was constructed differently and contained 320 rows.

The SVM model on the first dataset yielded 100% accuracy metrics, but it was less accurate on the second dataset. The SVM on the second data set resulted in a 99% overall accuracy score and 99% sensitivity or recall. Aqlan, Markle, and Shamsan (2017) achieved at 97.5% overall accuracy for their SVM model on 320 samples and 17 features.

Several conclusions were derived from this project. First, the initial dataset with 158 rows and all features results in 100% accuracy metrics for the Random Forest and the SVM. The random forest performed equally well on the second dataset. However, the SVM did not perform as well on the second dataset (df3) as compared to the first (df2). The second dataset with less features did influence the performance of SVM. Lastly, the dataset is easy to classify using these machine learning techniques.  A chart summarizing the overall accuracy is listed below.

Oveall Accuracy Score by Model and Data Set

| Data | SVM | RF |
|:---|:---:|:---:|
| df2 (158 samples, 24 features) | 100% | 100% |
| df3 (400 samples, 17 features)| 99% | 100% |
| Aqlan, Markle & Shamsan (2017)|97.5%| 100% |
