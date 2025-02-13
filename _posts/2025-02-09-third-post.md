---
layout: post
title: "Child Mind Institute competition - 1st place"
date: 2025-02-09
---


The competition [I will look at is Child Mind Institute — Problematic Internet Use](https://www.kaggle.com/competitions/child-mind-institute-problematic-internet-use).

The first place solution is by [Lennart Haupts](https://www.kaggle.com/competitions/child-mind-institute-problematic-internet-use/leaderboard)

# The problem

It is a basic classification problem. Based on a number of features, one must predict the level of problematic internet usage exhibited by children and adolescents, based on their physical activity. The goal of this competition is to predict from this data a participant's Severity Impairment Index (sii), a standard measure of problematic internet use. Sii has four categories: 0 for None, 1 for Mild, 2 for Moderate, and 3 for Severe.

The submission file will be a table with two columns: user ID and his or her sii.

The evaluation method is: [quadratic weighted kappa](https://www.kaggle.com/code/aroraaman/quadratic-kappa-metric-explained-in-5-simple-steps), which measures the agreement between two ratings. This metric typically varies from 0 (random agreement between raters) to 1 (complete agreement between raters).

# Step by step solution

The first issue is getting all the data together. There are two sets of data. One regular set of train.csv and test.csv files. But there is a bunch of .parquet files, which is time series from a wearable device each user wore for a while. We can already see that we will have a problem of too much data - and probably too much noise.

Parquet files contain data from 996 unique users. Instead of using the title of each feature (enmo, anglez, non-wear_flag,...), the author of the notebook replaced all titles by general column titles (stat 1, stat 2", etc.)

The train dafaframe has 3960 rows and 82 columns.
The train_ts (from parquet files) has 996 rows and 74 columns (id column is dropped).

Standard scaler is used to standardise numbers in train_ts.
All missing values are filled with the mean.

Principal Component Analysis is used to reduce all 74 features to just 15 (now called PC_1, PC_2. etc.)

IDs are reintroduced into the dataframe. And then all dataframes are merged by ID. This produces one big dataframe with 3960 rows and 97 columns.

It then removes many outliers with the clean_features function it created. The author explains in his write-up: Implausible values, such as body fat percentages over 60% or negative bone mineral content, were removed and replaced with NaN.

Some nummerical values are changed to categorical. For 15 hand-picked columns, values are classified in 10 bins. Each bin has about 200 rows in it. The author write: "Quantile binning was applied to a good chunk of the features to deal with the noise. Which worked surprisingly well.”

Next up a bit of cleaning: rows without the target variable sii are removed. All columns that are not present in the test set are stored in “features”.
y_model is the model target PCIAT-PCIAT_Total
y_comp is the competition target sir

A distribution graph of the target variable revealed there are too many zeroes.

A LassoCV method is used to impute values to nAn cells. The method aims to impute missing values in a dataset by training a predictive model for each feature with missing data, using other available features as predictors. If insufficient data is available to train a reliable model, it falls back on using the mean value for imputation.

This approach is similar to multivariate feature imputation techniques, such as those implemented in scikit-learn’s IterativeImputer, which models each feature with missing values as a function of other features and uses that estimate for imputation.

The author writes: Feature selection was done manually based on feature importance, reducing the dataset to 39 features. I wonder why 39, and not 20 or 50. The balance to strike is: having too many features makes the model overfit. Having to few makes it unsufficient. I do not know how the author found the right balance.

## The model

Now for the model.



