# Loan Default Predictor

## Introduction:

This project focuses on developing models to analyse merchants' payment footprints in the context of loan disbursement. The models incorporate various financial and transactional characteristics of merchants, including loan-sales ratios, transaction variability, customer concentration (Herfindahl-Hirschman index), and more. The project involves calculating key financial metrics, performing data transformations, and using different machine learning techniques to provide insights into merchant behavior and improve loan underwriting decisions.

## Dataset Description:

| **Variable Name**              | **Description**                                                                 |
|---------------------------------|---------------------------------------------------------------------------------|
| merchant_code                   | Merchant Identifier                                                             |
| relationage                     | Age of relationship with the payment company at the time of disbursal (in months)|
| mdisburse                       | Month of loan disbursal                                                         |
| loanamount                      | Principal amount                                                                |
| lsratio                         | Loan-sales ratio. Loan amount divided by average daily sales (91-day period)    |
| rtsshort                        | Loan-sales ratio calculated with average daily sales (28-day period)            |
| log_avg_transday                | Average of total daily transaction value (in log)                               |
| log_avgtrans                    | Average transaction sizes (in log)                                              |
| log_custcount                   | Number of distinct customers within period (in log)                             |
| cv_trans                        | Coefficient of variation of transaction sizes                                   |
| cv_transday                     | Coefficient of variation of total daily transaction values                      |
| HH_cust_trans                   | Herfindahl-Hirschmann index of customers' total transaction value               |
| avg_inactivity                  | Average of periods without any transactions (inactive days/total transaction days)|
| days_since_max_inactivity        | Days since the period of longest inactivity                                     |
| days_since_lasttrans            | Days since last transaction                                                     |
| max_trans_dt                    | (Relative to disbursal) Day with the largest transaction value                  |
| max_transcount_dt               | (Relative to disbursal) Day with most number of transactions                    |
| dayspast_freqcust               | Days since last transaction of most frequent customer at disbursal              |
| dayspast_largcust               | Days since last transaction of largest customer at disbursal                    |
| shr_Mon_trans                   | Share of total transaction value conducted on Mondays                           |
| shr_Tue_trans                   | Share of total transaction value conducted on Tuesdays                          |
| shr_Wed_trans                   | Share of total transaction value conducted on Wednesdays                        |
| shr_Thu_trans                   | Share of total transaction value conducted on Thursdays                         |
| shr_Fri_trans                   | Share of total transaction value conducted on Fridays                           |
| shr_Sat_trans                   | Share of total transaction value conducted on Saturdays                         |
| shr_Sun_trans                   | Share of total transaction value conducted on Sundays                           |
| \..._da,   ..._dr,   log\_..._da      | Relative changes (with subscript _dr) in payment variables measured in levels above. Absolute changes (with subscript _da) in payment variables measured as a share above. Changes are calculated between 28-day period prior to dis- bursal and 28-day period spanning 63-day to 91-day before disbursal. Absolute change in log variables (log_. . . ._da) also approximate relative change.                           |


## Data Exploration:

Through the use of Box Plots, the attributes containing outliers have been identified visually.

The skewness of these features is reduced through Interquartile Range (IQR) method. The IQR methods detects outliers which are present above the specified Upper Limit and specified Lower Limit. It caps the outliers present above the Upper Limit to the Upper Limit and caps the outliers present below the lower limit to the Lower Limit of the feature. Hence the skewness in each specified feature was reduced.

This imbalance has been addressed through 2 common techniques:

- Oversampling

- Undersampling

The results are observed after applying both approaches.

## Model Selection And Training:

### Model Datasets:

| **Variable Name** | **PF Basic** | **PF Deep** | **PF Basic + Loan Char** | **PF Deep + Loan Char** | **PF Basic + Merchant Char** | **PF Deep + Merchant Char** | **PF Basic + Loan Char + Merchant Char** | **PF Deep + Loan Char + Merchant Char** |
|-------------------|--------------|-------------|-------------------------------------|------------------------------------|------------------------------------------|-----------------------------------------|----------------------------------------------------------------|-----------------------------------------------------------------|
| relationage                       | ||||||||                                                                 |
| mdisburse                         | ||||||||                                                                 |
| loanamount                        | ||||||||                                                                 |
| lsratio                           |X||||||||                                                                 |
| rtsshort                          |X||||||||                                                                 |
| log_avg_transday                  |X||||||||                                                                 |
| log_avgtrans                      |X||||||||                                                                 |
| log_custcount                     | ||||||||                                                                 |
| cv_trans                          |X||||||||                                                                 |
| cv_transday                       |X||||||||                                                                 |
| HH_cust_trans                     | ||||||||                                                                 |
| avg_inactivity                    | ||||||||                                                                 |
| days_since_max_inactivity         | ||||||||                                                                 |
| days_since_lasttrans              | ||||||||                                                                 |
| max_trans_dt                      | ||||||||                                                                 |
| max_transcount_dt                 | ||||||||                                                                 |
| dayspast_freqcust                 | ||||||||                                                                 |
| dayspast_largcust                 | ||||||||                                                                 |
| shr_Mon_trans                     | ||||||||                                                                 |
| shr_Tue_trans                     | ||||||||                                                                 |
| shr_Wed_trans                     | ||||||||                                                                 |
| shr_Thu_trans                     | ||||||||                                                                 |
| shr_Fri_trans                     | ||||||||                                                                 |
| shr_Sat_trans                     | ||||||||                                                                 |
| shr_Sun_trans                     | ||||||||                                                                 |
| \..._da,   ..._dr,   log\_..._da  |X||||||||                                                                 |

### Data Splitting:
Test data: 30 % Training data: 70%

### Models Considered:

## Results After Hypertuning:

## Model Deployment:

## Visualisation:

## Summary of Results:

## Conclusion:

