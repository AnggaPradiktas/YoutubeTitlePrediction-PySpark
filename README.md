# Youtube Title Prediction Using PySpark

## Problem Statement
Indonesia is a really big nation with more than 200 million inhabitants, this make this country is one of the biggest market for many digital platform such as Youtube, Instagram, Facebook and many others. By this repository, I would like to try to predict which title on Youtube that perform best as seen on its views.

## Dataset
I collected the data based on top 45 youtube channel rank in [socialblade.com](https://socialblade.com/youtube/top/country/id) as per May 2019.![image](https://github.com/AnggaPradiktas/YoutubeTitlePrediction-PySpark/blob/master/image/top45socialbladeindo.png) And then I putted it into Big Query cause the data is pretty large (400-500MB).

## Data Preprocessing
Here we want to use a supervised learning using classification, but our data doesn't have any classification yet so that we need to preprocess the data to determine the classes. We selected video views that less than equal 5,000,000 to avoid outliers and then created classes as we named it 'viewGroup'. 
![image](https://github.com/AnggaPradiktas/YoutubeTitlePrediction-PySpark/blob/master/image/df_title%20head.png)
Here is you can access the code on [Preprocessing Youtube Title.ipynb](https://github.com/AnggaPradiktas/YoutubeTitlePrediction-PySpark/blob/master/Preprocessing%20Youtube%20Title.ipynb)

## Training and Testing the Data
We trained the data using [PySpark](https://spark.apache.org/docs/latest/api/python/index.html) cause we were dealing with pretty large text data and it would run really slow it we use pandas. After that we need to initiate the SparkSession in our local machine.

## Build a Pipeline Model
Build a pipeline using PySpark ML and convert the classes using OneHotEnconder so we could analyse further using Logistic Regression. Here you can find the [code](https://github.com/AnggaPradiktas/YoutubeTitlePrediction-PySpark/blob/master/Prediction%20Using%20Spark.ipynb).

## Output
We tried to train using Logistic Regression and Logistic Regression using TFIDF. 
<br>
<br>
Logistic Regression
![image](https://github.com/AnggaPradiktas/YoutubeTitlePrediction-PySpark/blob/master/image/lr.png)
![image](https://github.com/AnggaPradiktas/YoutubeTitlePrediction-PySpark/blob/master/image/lr_acc.png)

Logistic Regression TFIDF
![image](https://github.com/AnggaPradiktas/YoutubeTitlePrediction-PySpark/blob/master/image/lr_idf.png)
