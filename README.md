# User_Behavior_Logs_Quick_Analysis

This project is to clean, explore, analyze and build ML models from user behavior data. The purpose of this project is to help the analysts quickly catch the overall performance of a given dataset via several high-level notable features.

## Introduction

This project is originated from a UC Berkeley Graduate Seminar [Python Computing for Data Science](https://github.com/profjsb/python-seminar). This GitHub repo contains all the codes and a sample dataset for testing purpose. The objectives of this project are:
+ Clean dirty log data and transform it for analytics.
+ Exploratory data analysis, e.g. find user activity levels for different events, and user interaction with web components.
+ Find the conversion rate of users, identify key factors that bottleneck the conversion rate.
+ Propose any hypothesis and test using selected features.
+ Build machine learning models to predict user behaviors, including but not limited to signup, churn, etc.
+ Discover interesting insights in the dataset and suggest how to improve the user signup rate.

## Requirements & Getting Started

Clone this repo onto your local mechine.
```
git clone https://github.com/leoli3024/User_Behavior_Logs_Quick_Analysis.git
```
Then install the necessary geological information package:
```
pip install geoip2
```
Other dependencies include:
```
numpy
pandas
matplotlib
scikit-learn
pylab
```
Now download the geoip2 databases from:
 - City GeoIP - http://geolite.maxmind.com/download/geoip/database/GeoLite2-City.tar.gz
 - Country GeoIP - http://geolite.maxmind.com/download/geoip/database/GeoLite2-Country.tar.gz

and unzip the compresses files to the /data folder
 - data/GeoLite2-City_20180501/
 - data/GeoLite2-Country_20180501/

Then open and run the notebook files in order, from 0_Summary_Statistics to 3_Supervised_Learnings.

## Data Sources

A sample dataset called ```UBA_sample_data``` could be found in the data directory. This is the sample dataset used to test the funcionalities of all four files. Running the notebook files in order (0 to 3) would generate the additional data files that might/will be used in the rest notebooks. The dataset is in JSON format, which is the most common format for User Logs. Dataset contains cache log information of *SOME* website's main webpage for a week, including actions on leaving the webpage, click a button, send verification code, apply for account, and etc. Information can be sensitive here, so the name of the website would not be revealed. 

## Contents of the code

The basic idea behind this project is to develop some tools for product analysts and or marketing analysts to gain decent understandings of any given datasets about user behaviours from user logs. Oftenly such analyses are achieved using SQL, Excel or Tableau, which means that whenever there comes a new dataset, the analysts need to go through the whole process step-by-step again. This project is aiming to solve such issues by operating the most common analyses on a given dataset together, and integrating and differentiating these steps into stages, seen as ```0_Summary_Statistics.ipynb```, ```1_Cleaning_Processing_EDA.ipynb```, ```2_Feature_Analysis_Selection.ipynb```, and ```3_Supervised_Learnings.ipynb``. 

In ```0_Summary_Statistics.ipynb```, we spend some time looking at the keys (features) of the datasets, and detailed formats and contents of sample features. We would also take several quick views on the distributions and counts of a few most commonly used features, such as EVENTS, PAGE CLICKS, USER BROWSERS, and STAY TIME, etc. These overviews/high-level understandings would help the analysts quickly pick up the performances of a given dataset, and those experienced analysts to layout the key points they might want to keep in mind in future analysis. Eg. clicksubmit ~= formsubmit in most cases; if there exists a dataset with clicksubmit >> formsubmit, then there might be some technical issues with form submissions/submission page loading. 

In ```1_Cleaning_Processing_EDA.ipynb```, we are working on data cleaning and basic exploratory data analysis (EDA). For future work and references, it's always great to keep the original data file while making a copy of a cleaned-version of it. The goal, and the output, of this notebook is to generate a cleaned and well-formated dataset - ```cleaned_data.csv```. We also study the counts, unique values and missing values, etc. in each feature, which would be of help when analyzing the conversion rate in a more detailed manner. In this notebook, we only study the overall rates (regardless of if there exists missing values) on selected features.

In ```2_Feature_Analysis_Selection.ipynb```, the ultimate goal is to find and select the useful features for sign-up prediction. With missing values either dropped out or filled, we learn the composition of sign up/conversion rate based on the performances of specific features. Cleaning the missing values also enables analysis on the distribution/composition and statistics of a feature, and correlations between features, seen as scatter_matrix. Further cleaned dataframe, with only selected features, exports another dataset - ```selected_data.csv```, which would be used for building Machine Learning Models later.

In ```3_Supervised_Learnings.ipynb```, with the selected features after feature performane analyses from the previous notebook, we start to develop machine learning models to predict user behaviors. We build and compare the results of Logistic Regression Models, Decision Trees (Single and Bagged), K-Nearest Neighbors (Single and Bagged), Random Forest, Gradient Boosting Tree, MLP Neural Network, and Linear & Non-Linear SVM. Lastly, from the metrices scores and ROC curves of each model, we apply a hyper-parametering tuning on a selected model (Random Forest). Analysts/Users can later choose to either continue to work with these models or affine/refine the models. 

## Testing the code

This project was built upon another dataset and tested with the ```UBA_sample_data.txt```. There might still exists some limitations/non-functional edge cases since all User Logs I can access are in similar formats with similar keys, but all these four notebooks work fine and smoothly with the sample dataset. The ```0_Summary_Statistics.ipynb``` and ```1_Cleaning_Processing_EDA.ipynb``` make sure further analyses are not based on hard-calling columns in the dataframe, but on the pre-defined arrays for features. Users/Analysts can choose to turn off some features/arrays by assigning ```None``` value (disabling plotting involving these arrays) or filling the array with ```NaN``` (disabling plotting involving these arrays) or ```0``` (enabling plotting involving these arrays but plots would be of less info and meaning). All notebook files come with saved outputs and plots and loads datasets generated within this project to quickly show that the testing case with sample dataset is successful. There isn't much to set up for running the notebook files; for printed out results using sample dataset, please see [/Capture](https://github.com/leoli3024/User_Behavior_Logs_Quick_Analysis/tree/master/Captures), and for a video showcasing how to run these files, the [video](https://drive.google.com/file/d/1EjyWj2cC_HsgGtnGX_sPOx4b5enBDiBA/view?usp=sharing) is shared via Google Drive. 

## Results

The capture html files exported using `UBA_sample_data.txt` shows that the testing case were indeed successful. Several outputted plots using sample set are included below, to further showcase the working condition and what types of outputs are we getting from this project. **Screen captures were originally requested to prove the working condition, but this project contains 4 notebook files and each consists of at least 100 cells.** It would be complicated and inconvenient to take screenshots of the running cells. Instead, I export the files into html format, from which you could see all files have been re-runned through the beginning indicated by number 1 next to the first cell, and consecutive numbers in the followings. In addition to the outputted plots and figures shown below, you could find the [html-captures](https://github.com/leoli3024/User_Behavior_Logs_Quick_Analysis/tree/master/Captures) or [video](https://drive.google.com/file/d/1EjyWj2cC_HsgGtnGX_sPOx4b5enBDiBA/view?usp=sharing), both of which are served as replacements of the screen captures.

![](https://github.com/leoli3024/User_Behavior_Logs_Quick_Analysis/blob/master/conversationrate.png)

**Figure 1:** High-level conversion rates based on specific commonly-used features.

![](https://github.com/leoli3024/User_Behavior_Logs_Quick_Analysis/blob/master/timescatter_signup_split.png)

**Figure 2:** Plot of correlations between sample features.

![](https://github.com/leoli3024/User_Behavior_Logs_Quick_Analysis/blob/master/features.png)

**Figure 3:** Correlations between selected features with sign up rates.

![](https://github.com/leoli3024/User_Behavior_Logs_Quick_Analysis/blob/master/ROC_Random_Forest.png)

**Figure 4:** ROC curve of Random Forest model.

![](https://github.com/leoli3024/User_Behavior_Logs_Quick_Analysis/blob/master/ROC_selected_RF_tuned.png)

**Figure 5:** ROC curve of Random Forest model after tunning parameters.

**ROC curves of other models could be found under this directory. Because of the space, only the ROC curves, before and after tunning, of the selected model are displayed above.**
