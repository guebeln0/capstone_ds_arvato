# Create a Customer Segmentation Report for Arvato Financial Solutions

## Data scientist Udacity Nanodegree - Capstone Project

This project is part of the Udacity course for Data Scientist. The corresponding Blog can be found on <a href="https://medium.com/@nicolas.guebel/who-should-i-mail-or-getting-to-know-your-customers-2e3bbcda3d8b">medium</a>.

## Table of Contents
- [Project Overview](#projectoverview)
- [Data Description](#datadescription)
- [Files Description](#filesdescription)
- [Technical Overview](#technicaloverview)
- [Results](#results)
- [Requirements](#requirements)
- [Acknowledgments](#acknowlegments)
- [License](#license)


<a id='projectoverview'></a>
## Project Overview
Which company has not wondered, what makes their customers special and if could only mail a certain amount of customers, which are most likely to respond?

### Question 1: what makes our customer special?
After cleaning the data, we will try to identify groups in the overall population. We use for that purpose an unsupervised learning method with KMeans and PCA preprocessing.

### Question 2: who is more likely to respond?
To answer this question, we use a mailout dataset, which states whether or not a customer has responded to a mailout. We will use here a supervised learning approach and compare several classifier models to see, which performs best.

<a id='datadescription'></a>
## Data Description
The datasets are not publicly available and according to the terms and conditions were only used for this project with Udacity.
- Udacity_AZDIAS_052018.csv: Demographics data for the general population of Germany; 891 211 persons (rows) x 366 features (columns).
- Udacity_CUSTOMERS_052018.csv: Demographics data for customers of a mail-order company; 191 652 persons (rows) x 369 features (columns).
- Udacity_MAILOUT_052018_TRAIN.csv: Demographics data for individuals who were targets of a marketing campaign; 42 982 persons (rows) x 367 (columns).
- attribute_list.csv: list of the attributes described in the dataset and type of the attributes

<a id='filesdescription'></a>
### Files Description
- Arvato Project Workbook_v3.ipynb: Notebook containing data exploration and visualisations
- attribute_list.csv: list of the attributes described in the dataset and type of the attributes used during cleaning

<a id='technicaloverview'></a>
## Technical Overview
The Notebook is structured in 3 main parts:
- Part 0: We will get to know the data, assess data quality, define necessary cleaning steps.
  - gather: reading csv files
  - assess: after loading the files into pandas, data quality assessments are made and possible changes
  - clean: functions for cleaning rows, columns with missing values, clean mixed datatype and imputing values.
  - analyze: several analysis are performed to find necessary cleaning steps
- Part 1: Customer segmentation using PCA & KMeans
  - clean: One Hot encoding of categorical variables
  - model: PCA and KMeans are performed
  - visualize: cluster distribution for general population and customer are plotted
  - analyze: trace back the most important features for the cluster with the most differences
- Part 2: Supervised learning: who is more likely to respond
  - clean: cleaning for the mailout dataset
  - model: different classifier are evaluated

<a id='results'></a>
## Results:
I encourage you to read the results on <a href="https://medium.com/@nicolas.guebel/who-should-i-mail-or-getting-to-know-your-customers-2e3bbcda3d8b">medium</a>.

### Question 1: what makes our customer special?
After an extensive data cleaning and encoding, we used a PCA model to reduce the number of features used (from 361 to 127) keeping 80% of the variance of our data.
In a next step, we build cluster in the population and compaired it with our customers. Cluster 3 & 9 as well as Cluster 0 and 1 are most different between the two groups.
Finally we could express our Cluster in term of important features. Our customer seem to be wealthier, having higher spec car and living in the west of Germany.

### Question 2: who is more likely to respond?
We wanted to know if we could predict “who is more likely to respond?”. We created a Classifier with an ROC AUC score of 0.62. This can then be used to include in future campaign customer that are more likely to respond.

<a id='requirements'></a>
## Requirements:
required python packages: pandas, numpy, matplotlib, sklearn, xgboost

<a id='acknowlegments'></a>
## Acknowledgments
Dataset credit: Udacity and Arvato on <a hef="https://www.kaggle.com/competitions/udacity-arvato-identify-customers/overview">Kaggle</a>
Tutorial in using PCA & KMeans in <a href="https://365datascience.com/tutorials/python-tutorials/pca-k-means/">365datascience</a>.

<a id='license'></a>
## LICENSE: MIT license
