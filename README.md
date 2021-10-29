# Data Analytics/Big Data Certificate — Python and R  
 
 
### by Marcelo Jimenez, Petroleum Engineering Graduate from The University of Texas at Austin 🤘

___
### <ins> Introduction </ins>

Right after graduation and over the summer of 2021, I worked towards this Data Analytics certificate as I wanted to broaden my skill set. Coding and Data Analysis always intrigued me and decided to deepen my knowledge so that I could one day use it in the Petroleum Engineering industry. This Repository coresponds to all the projects I did in Python and R to complete my certificate. 

Below is a Summary of the aim and results of the various projects I completed. The complete description and lines of code are located inside this repository and are linked in this summary.
___

### <ins> Course Objectives and Outcomes </ins>


* Identify types of business problems for which data analysis can provide significant insights in support of **business decision-making**.

* Translate business objectives into analytical opportunities using **data mining**.

* Select and justify **appropriate types of data** analysis and statistical procedures

* Apply **data analytics in eCommerce** (e.g., understanding customer behavior, segmenting customers by key demographic factors, selecting new products strategically and predicting their profitability).

* Become broadly competent in the use and evaluation of **statistical machine learning techniques** of classification, regression and association.

* Apply **dimensionality reduction** methods to broad datasets to reduce their complexity prior to modelling

* Identify and solve collinearity through feature engineering and **feature selection**

* Interpret the results of data analysis to **make models and predictions** and to establish the reliability of those predictions.

* Acquire, process, and **analyze extremely large data sets** using cloud-based data mining methods to discover patterns or do data exploration.

### <ins> Course Summary </ins>


Course 1 <br /> Examining Customer Demographics | Course 2 <br />Predicting Customer Preferences | Course 3 <br />Data Analysis and Visualization | Course 4 <br /> Data Science & Big Data
:------------: | :-------------: | :------------:|:-------------:|
Python         |      R          |       R       |   AWS & R
1\) Perform Exploratory Data Analysis on customer demographics data using numpy, pandas, seaborn, and matplotlib.<br /> <br /> 2) Identify which customer attributes relate significantly to customer default rates and to build a predictive model that the business can use to classify potential customers ‘at-risk’.| 1) Use machine learning methods to predict which brand of computer products customers prefer based on customer demographics. <br /> <br /> 2) Determine associations between products that can be used to drive sales-oriented initiatives. | 1) Modeling patterns of energy usage by time of day and day of the year in a typical residence whose electrical system is monitored by multiple sub-meters. <br /> <br /> 2) Determining a person’s physical position in a multi-building indoor space using wifi fingerprinting. | 1) Use AWS Elastic Map Reduce (EMR) platform to collect large amounts of smart-phone preference data from the Common Crawl, then compile it into a single data matrix. <br /> <br /> 2) Use hand assesed smart phone sentiment data matrices to develop predictive models and then apply these models to the data collected.

### <ins> Highlights </ins>

#### Course 1 - Examining Customer Demographics

Importing Data

```
all_data = pd.read_csv("./Demographic_Data.csv")
all_data.head()                      
```

Decision Tree & Random Forest

```
dtc = DecisionTreeClassifier(max_depth=5)
dtc_model = dtc.fit(X_train, y_train)

rfc = RandomForestClassifier(n_estimators=500, n_jobs=2, random_state=0)   #.values gives the values in an array of shape (n,1)
rfc_model = rfc.fit(X_train, y_train.values.ravel())     #.ravel() converts array to shape (n,)
```

<a href="https://raw.githubusercontent.com/Mar-Jim/Mar-Jim/main/Assets/Data%20Analytics/1Mod1.png">
  <img src="https://raw.githubusercontent.com/Mar-Jim/Mar-Jim/main/Assets/Data%20Analytics/1Mod1.png" height="30">
</a>

Simple correlation
```
corr_mat = all_data.corr()   #checking for correlation just incase (realtionships between features)
print(corr_mat)
```
Visualizations

```
from sklearn import tree – for Decision tree visualization
sns.heatmap – for correlation visualization
```

<a href="https://raw.githubusercontent.com/Mar-Jim/Mar-Jim/main/Assets/Data%20Analytics/1Pred1.png">
  <img src="https://raw.githubusercontent.com/Mar-Jim/Mar-Jim/main/Assets/Data%20Analytics/1Pred1.png" height="30">
</a>

<a href="https://raw.githubusercontent.com/Mar-Jim/Mar-Jim/main/Assets/Data%20Analytics/1Pred2.png">
  <img src="https://raw.githubusercontent.com/Mar-Jim/Mar-Jim/main/Assets/Data%20Analytics/1Pred2.png" height="30">
</a>

EDA

<a href="https://raw.githubusercontent.com/Mar-Jim/Mar-Jim/main/Assets/Data%20Analytics/EDA1.png">
  <img src="https://raw.githubusercontent.com/Mar-Jim/Mar-Jim/main/Assets/Data%20Analytics/EDA1.png" height="30">
</a>

<a href="https://raw.githubusercontent.com/Mar-Jim/Mar-Jim/main/Assets/Data%20Analytics/EDA2.jpg">
  <img src="https://raw.githubusercontent.com/Mar-Jim/Mar-Jim/main/Assets/Data%20Analytics/EDA2.jpg" height="30">
</a>

Pandas Profiling
```
pandas_profiling.ProfileReport(df)
```

<a href="https://raw.githubusercontent.com/Mar-Jim/Mar-Jim/main/Assets/Data%20Analytics/EDA3.png">
  <img src="https://raw.githubusercontent.com/Mar-Jim/Mar-Jim/main/Assets/Data%20Analytics/EDA3.png" height="30">
</a>

Prediction
```
y = amount_default
y2 = amount_not_default
X = only_default[only_default.columns.difference(['LIMIT_BAL'])]
X2 = only_not_default[only_not_default.columns.difference(['LIMIT_BAL'])]

X1_train, X1_test, y1_train, y1_test = train_test_split(X, y, test_size=0.20, random_state=123)
X2_train, X2_test, y2_train, y2_test = train_test_split(X2, y2, test_size=0.20, random_state=123)

rfc = RandomForestClassifier(n_estimators=200, n_jobs=2, random_state=0)   #.values gives the values in an array of shape (n,1)
default_model = rfc.fit(X1_train, y1_train.values.ravel())     #.ravel() converts array to shape (n,)
not_default_model = rfc.fit(X2_train, y2_train.values.ravel())

default_pred = default_model.predict(X1_test)
not_default_pred = not_default_model.predict(X2_test)

metrics.accuracy_score(y1_test, default_pred)
Accuracy =  0.36814276272306673

metrics.accuracy_score(y2_test, not_default_pred)
Accuracy =  0.6038167938931298
```

<a href="https://raw.githubusercontent.com/Mar-Jim/Mar-Jim/main/Assets/Data%20Analytics/Pred1.png">
  <img src="https://raw.githubusercontent.com/Mar-Jim/Mar-Jim/main/Assets/Data%20Analytics/Pred1.png" height="30">
</a>


<a href="https://raw.githubusercontent.com/Mar-Jim/Mar-Jim/main/Assets/Data%20Analytics/Pred2.png">
  <img src="https://raw.githubusercontent.com/Mar-Jim/Mar-Jim/main/Assets/Data%20Analytics/Pred2.png" height="30">
</a>

#### Course 2 - Predicting Customer Preferences


#### Course 3 - Data Analysis and Visualization


#### Course 4 - Data Science & Big Data


*Marcelo Jimenez*
