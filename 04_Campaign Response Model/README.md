# Campaign Response Model
[![](https://img.shields.io/badge/-Python-blue)](#) [![](https://img.shields.io/badge/-XGBoot-blue)](#) [![](https://img.shields.io/badge/-SMOTE-blue)](#) [![](https://img.shields.io/badge/-RandomizedSearchCV-blue)](#)

**Notebooks:** [Campaign_Response_Model](./Campaign_Response_Model.ipynb)  
**Google Colab:** [![Open In Collab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/TSupattra/BADS7105_CRM/blob/main/04_Campaign%20Response%20Model/Campaign_Response_Model.ipynb)  

## Data set : [Retail_Data_Response](./Retail_Data_Response.csv) [Retail_Data_Transactions](./Retail_Data_Transactions.csv) 


Use data set 3 years back

![CampaignRM_01](./CampaignRM_01.JPG)


## Data Preparation

**RFM model**

![CampaignRM_02](./CampaignRM_02.JPG)

- R (Recency) คือ ระยะเวลาที่ลูกค้ามาใช้บริการครั้งสุดท้าย ล่าสุดเมื่อไหร่
- F (Frequency) คือ ความถี่ที่ลูกค้ามาใช้บริการ
- M (Monetary) คือ จำนวนเงินทั้งหมดที่ลูกค้าใช้จ่าย


**Customer Lifetime Value (CLV) Model**

![CampaignRM_03](./CampaignRM_03.JPG)


**Fixing imbalanced with SMOTE**
Problem imbalanced data

![CampaignRM_04](./CampaignRM_04.JPG)

Use SMOTE in Train data of RFM and CLV

    sm = SMOTE(random_state=0)

    sm.fit(X_train_rfm, y_train_rfm)
    X_SMOTE_rfm, y_SMOTE_rfm = sm.fit_resample(X_train_rfm, y_train_rfm)

    sm.fit(X_train_clv, y_train_clv)
    X_SMOTE_clv, y_SMOTE_clv = sm.fit_resample(X_train_clv, y_train_clv)


## Result
**Logistic regression**

![logistic_regression_model_SMOTE_RFM](./logistic_regression_model_SMOTE_RFM.png) ![logistic_regression_model_SMOTE_CLV](./logistic_regression_model_SMOTE_CLV.png)


**XGBoost model**

XGBoost hyperparameter search using scikit-learn RandomizedSearchCV

![CampaignRM_05](./CampaignRM_05.JPG) 

![XGBClassifier_SMOTE_RFM](./XGBClassifier_SMOTE_RFM.png) ![XGBClassifier_SMOTE_CLV](./XGBClassifier_SMOTE_CLV.png)



## Conclusion

AUC of XGXGBClassifier model SMOTE is higher than Logistic regression model with SMOTE 






