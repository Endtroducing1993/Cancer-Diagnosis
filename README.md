# Cancer-Diagnosis

**Cancer Diagnosis**

**Problem Statement:** Classify the given genetic variations/mutations based on evidence from text-based clinical literature. We have a total of 9 classes, the classes represent different levels of whether or not the variant is a driver or passenger mutation. Is irrelevant to the type of cancer.
              Thus it is a multiclass classification problem.

**Performance Metric:** In this problem we can’t afford to have predictions where the patient is diagnosed to be negative but is actually positive. Thus we choose a performance metric which penalizes wrong predictions. We also want to track the performance of our model, which we can get with the help of a performance metric. Thus we are choosing a multi-class log-loss and confusion matrix.

**Exploratory Data Analysis:**

**Understanding Data:**

**Shape of Data:** In our data we have 3321 data points and 3 features which add value to our prediction. Out of 3 features 2 features(Gene and Variation) are categorical whereas the text feature contains textual data.

**Missing Values:** We observe that neither Gene nor Variation feature has any missing values. But our text feature has missing values. The missing text values are replaced with the string containing the Gene and variation feature belonging to that data point.

**Preprocessing Data:** In the preprocessing stage we preprocess our text feature by removing stop words,removing special characters, converting text into lower case, removing extra spaces etc.

**Splitting The Data:** We split the data into train,test and cross validation data. We have chosen an 80:20 split ratio. As a result of which 64 percent get into training 20 percent in test and 16 percent into cross validation data. After splitting we get following number of data points in train,cv and test data:

**Train: 2124
Cross Validation: 532
Test: 665**

**Distribution of Classes:** Here we observe that we have highly imbalanced data with few classes occurring very often whereas few classes rarely occur. Below demographic conveys it all:

![image](https://user-images.githubusercontent.com/61081294/124265522-69479700-db53-11eb-85f7-0e80358b2918.png)

Number of data points in class 7 : 609 ( 28.672 %)
Number of data points in class 4 : 439 ( 20.669 %)
Number of data points in class 1 : 363 ( 17.09 %)
Number of data points in class 2 : 289 ( 13.606 %)
Number of data points in class 6 : 176 ( 8.286 %)
Number of data points in class 5 : 155 ( 7.298 %)
Number of data points in class 3 : 57 ( 2.684 %)
Number of data points in class 9 : 24 ( 1.13 %)
Number of data points in class 8 : 12 ( 0.565 %)

**Observation:** Class 7,4 and 1 occur the most whereas class 3,9 and 8 occur the least.

Featurization of Text Data: We have used **Response Coding** and **One hot encoding** to encode our features. Thus we train our models seperately on the features obtained from both the encodings.

**Univariate Analysis**

We first perform univariate analysis on 3 features **'Gene', 'Variation' and 'Text'** by training and testing each figure using Logistic regression. From which we infer that Gene and Text are the most useful features in our predictive modelling .Variation also proves to be a good feature but somewhat less useful in predictive modelling as compared to the **'Gene'** and **'Text'**.

**Predicitve Modelling**: We train our data using **MultinomialNaiveBayes, KNN, logistic regression,Support vector classifier, Random Forest, Stacking with Logistic regression as meta classifier**. And below are the results that we obtain.


![image](https://user-images.githubusercontent.com/61081294/124266320-71ec9d00-db54-11eb-8470-f8c638e8fc0f.png)

Observation: We infer **Logisitc regression** and **stacking** using Logisitce regression as meta classifier gives really good perfomance on the data.
