# AWS-SageMaker

Title: Retail Sales Prediction using AWS SageMaker XGBoost (Regression)

Description:

The objective of this project is to forecast weekly retail store sales based on historical data.

Dataset:

The data consists of three sheets:
- Stores
- Features
- Sales
The data contains holidays and promotional markdowns offered by various stores and several departments throughout the year.

Merge Dataset into one dataframe:

-The three dataframes are merged to form a single dataframe.
-The newly created dataframe contains following fields:
Store                
Dept                 
Date                 
Weekly_Sales         
IsHoliday            
Temperature          
Fuel_Price           
MarkDown1       
MarkDown2       
MarkDown3       
MarkDown4       
MarkDown5       
CPI                  
Unemployment         
Type                 
Size                 
month                

- The NaN values are replaced with zeros.
- Checked the duplicated entries in the dataframe.
- Replaced the "IsHoliday" with ones and zeros instead of True and False.

Exploratory Data Analysis:

- Created pivot tables to understand the relationship in the data. The results obtained are as follows:
  - Type A stores have much higher sales than Type B and Type C.
  - MarkDown2 and MarkDown3 have a higher volume on holidays compared to that of regular days.
  - While other MarkDowns don't show significant changes relating to the holiday.
  
Data Visualization:

- Histogram for each attribute.
- Weekly sales of each store type is shown by the bar plot.
- Department-wise weekly sales using a horizontal bar plot.

Prepare the training data:

- The dataset is split into 85% training data and 15% testing data.

Model Implementation:

1. XGBoost Regressor in Local Mode
    Parameters - learning_rate = 0.1, max_depth = 5, n_estimators = 100
    The result otained is as follows:
    
    Accuracy : 0.8220456771239986
    
    RMSE = 9622.919 
    
    MSE = 92600580.0 
    
    MAE = 6404.524 
    
    R2 = 0.8220456771239986 
    
    Adjusted R2 = 0.8212655476231603

2. XGBoost Regressor using SageMaker
   The result otained is as follows:
   
   RMSE = 7141.338 
   
   MSE = 50998708.0 
   
   MAE = 4271.1924 
   
   R2 = 0.8986535169832639 
   
   Adjusted R2 = 0.8982092266736509

Result:

The R2 values of both models show that XGBoost Regressor using SageMaker performs better (R2 = 0.89) than XGBoost Regressor in Local Model (R2 = 0.82).
