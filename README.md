# Capstone Project

## Predicting Churn for a Music Streaming Service (Sparkify)

This project is the capstone project of my Data Scientist Nanodgeree at Udacity. It's about identifying the users that 
are about to cancel the service. The data used here is a small subset of the original dataset. 

The aim of the project is to use Spark to wrangle the data, engineer features, and finally train a model that predicts
if users are about to cancel the service. 

I wrote a blog post that documents the process and some explanations on the steps taken in this project. 
You can find it [here]().

### Libraries

- pyspark
- pandas
- numpy
- matplotlib
- seaborn
- datetime

### Content

This repository hold the notebook "Sparkify.ipynb" with the code for this project. There are some comments in the 
code to give some guidance. 

### Summary

The data contains all events of a number of users - from login, listening to songs, to logout. Multiple events can be 
associated with a unique user. The user can be identified by the user-ID. Before building a model to make 
predictions, it is necessary to first define "churn" and prepare the data. In this case I went from a large dataset 
on the event-level to a small dataset on the user-level (one row per user). Accordingly, the features were extracted or
calculated on the user-level. 

The resulting model has a f1-score below 70% which is not ideal for deployment. There are different things to be 
considered for further improvement of the model:

- optimize the f1-score (which is a harmonic mean of recall and precision)? 
- mabe optimize precision or recall, depending on whether it is more acceptable to approach more/too many users with
an offer or not approach enough --> since it is harder to win new customers instead of keeping existing customers, the 
model should be optimized in a way that ideally all users that think about cancelling are being approached 

 

### Acknowledgements

The data was kindly provided by Udacity. The majority of the code was derived from the lessons provided in preparation 
for this project.

In addition, I found these pages to be very helpful:

Some Spark documentation:

[Vector Assembler](https://spark.apache.org/docs/latest/api/python/pyspark.ml.html#pyspark.ml.feature.VectorAssembler)

[Standard Scaler](https://spark.apache.org/docs/latest/api/python/pyspark.ml.html#pyspark.ml.feature.StandardScaler)

[Logistic Regression](https://spark.apache.org/docs/latest/api/python/pyspark.ml.html#pyspark.ml.classification.LogisticRegression)

[Random Forest Classifier](https://spark.apache.org/docs/latest/api/python/pyspark.ml.html#pyspark.ml.classification.RandomForestClassifier)

[Multiclass Classification Evaluator](https://spark.apache.org/docs/latest/api/python/pyspark.ml.html#pyspark.ml.evaluation.MulticlassClassificationEvaluator)

Some Stackoverflow help:

[Counting missing values in the dataframe](https://stackoverflow.com/questions/44627386/how-to-find-count-of-null-and-nan-values-for-each-column-in-a-pyspark-dataframe?rq=1)

[How to use flatMap for handling a list](https://stackoverflow.com/questions/22350722/what-is-the-difference-between-map-and-flatmap-and-a-good-use-case-for-each)

[Convert unix time](https://stackoverflow.com/questions/3682748/converting-unix-timestamp-string-to-readable-date)

