# Hackathon
**Task: to predict whether a bank user is in fraud status(1: yes 0: no) according to database's history records**
## dataset
You can download training & testing dataset from [GoolgeDrive]:  .

Each type includes three files, i.e. 

* user information
* user behavior 
* user transaction

These files are connected with their own unique indentity (ID).

## pre-process
We process the data mainly follwing the next steps:

1. feature selection. 

*note: features such as issue_d, emp_title, zip_code, addr_state make no sense, thus to be removed*

2. convert string feature to value feature.

*note: encode*

3. commbine all the features.

*note: feature joining according to ID.*

4. handle the Nan values.

*note: remove features including too many Nans, and fill others with the mean values of each type of feature*

5. feature normalization.

## train

We prepare training label with the *fraud_status* feature:

    0 if fraud_status={Normal_0,Normal_1,Suspect_0}
    1 if fraud_status={Suspect_1,Suspect_2,Fraud_0,Fraud_1,Fraud_2}

idle: feture exaction + xgboost

+ 80% for training and 20% for evaluating.

* after 15 epochs: eval-error:0.054921	train-error:0.051535

## test

The results are saved in result.csv with the format of {ID,result}.
