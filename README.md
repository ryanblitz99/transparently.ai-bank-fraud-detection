# Table of contents

- [Introduction](#Introduction)

- [Data](#Data)

- [folder descriptions](#folder_description )

- [Conclusions](#Conclusions)

#### Introduction

The goal of the project is to:

1. From Wharton database, retrive important data such as liquidity ratios and 'AAER', which indicates if a company has been indicted for account manipulation, and join it with the banks dataset. This step has already
been done and due to the file size constraints, I am unable to upload the original banks dataset.
2. Extract transform load procedures
3. Exploratory data analysis and log transformation to deal with the skew of our data
4. Build and evaluate machine learning models to predict the probability of a company beeing inidcted for account manipulation(AAER == 1)

#### Data

1. banks_final_aaer.rds: raw data of banks joined with AAER( takes values of 0,1)
2. banks_cleaned_with_AAER.rds: cleaned dataset with additional items from wharton database joined together on code and year. This is the dataset that we will be using to train our models
3. AAER_WITH_ISIN.xlxs: AAER data containing the ISIN and CIK code of the banks involved.

#### folder_descriptions

1. AAER_preprocessing_data: all the raw AAER excel data that was combined and used to get the final AAER dataset
2. data_wrangling_scripts: All of the data wrangling scripts used
3. finalised_data: finalised data
4. graphs: all the graphs in the QMD report
5. items_data: all the data of the fields extracted from wharton database in excel format
6. Group 2 Transparently.AI Project V3: rendered HTML file of the QMD as well as the QMD file. Refer to the HTML for the full report and analysis

#### Conclusions

After trying 3 distinct methods: logistic regression, lasso and xgboost, we have conncluded that the logistic regression model `log.fit4.2` performs the best with the highest AUC of 0.85 and the 3rd lowest AIC,
which quantifies the relationship between model complexity and goodness of fit. However, there are limitations to this, since there are an overwhelming number of AAER == 0 in the dataset, the high AUC could be misleading.
However, the model has a decent sensitivity of 0.75 which indicates that it does a decent job at descerning positives from negatives despite its low precision. Ultimately, the accuracy of our chosen model is 98%.


