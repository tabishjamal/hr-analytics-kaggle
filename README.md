# HR Analytics: Job Change of Data Scientists
## Challenge: https://www.kaggle.com/arashnic/hr-analytics-job-change-of-data-scientists
#### Accuracy 73.88% 
#### Result can be improved by doing more data cleaning 

## Steps Taken
#### 1. Exploratory Data Analysis
* Check for Missing Values
* Check for Data Imbalance

#### 2. Data Cleaning
* Treating Missing Values
  * Deleting instances where 7 out of 14 cells are null, because they have very less information in them
  * Fill **gender** with "undisclosed" where 'NaN' is present and "diverse" where 'Other' is present 
  * enrolled_university and education_level --> fill with mode
  * Company_Size and Company_Type to be filled with ffill values
  * Fill **Last_new_job** with values present in **experience** where 'Never' and 'Nan' are present
* Data Transformation
 * One Hot Encoding: major_discipline, gender, enrolled_university, and company_type
 * Label Encoding: education_level, and relevent_experience
 * Experience, Current Job Experience, and Company Size: Data has been cleaned first, by removing > and < values by ceil and floor values respectively. And both the columns has been changed from object to int.

#### 3. Treating Imbalance Data and Train Test Split
 * First separate Train and Validation set by 80-20 division
 * On Test set, apply Oversampling, SMOTE. We will use both dataset and compare F-1 Score to choose model

#### 4. Modelling
 * Logistic Regression
 * Decision Tree
 * Random Forest
 * (Other models such as xgBoost can also be used)

#### 5. Model Selection and Evaluation
 * Decision Tree with tree depth = 6
 * F-1 score and AUC has been used for Evaluation metrics. Because data is imbalanced.
