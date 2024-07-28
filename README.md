Name:Adarsh mishra  
Company:CODTECH IT SOLUTIONS  
ID:CTO8DS3576  
Domain:ARTIFICIAL INTELLIGENCE  
Duration:JULY 1st 2024 to AUGUST 1st 2024  


# Overview of the project:
__PROJECT:Data-Preprocessing__  
__objective__:  
The objective of this Project is to perfom Data-PreProcessing on any dataset.Data processing involves tranforming raw data into a clean and usable format
to ensure machine learning algorithms can process it effectively.  
__Steps_Involving__:   
1) Data cleaning- Handling missing values ,correcting errors and removing outliers  
2) Data Encoding- encoding numerical and categorical data's for handling missing values  
3) Data scaling- adjusting the range of the feature value by using Normalization and Standardization  
4) Data splitting - Dividing the dataset into training ,validation and testing sets

__Technology used__:  
1) Python- python is widely used for data preprocessing due to its extensive libraries  
2) Pandas- essential library for data manipulation and analysis  
3) NumPy- used for numerical computing and handling arrays  
4) scikit-learn- provides range of supervisied and unsupervisied learing algorithms

__Importance__  
Data preprocessing is vital as it directly impacts the performance and accuracy of machine learning models.By ensuring data is clean,consistent and properly formatted,
data processing helps in building robust models that provide reliable and meaningful insights.  

__Expalanation__:  
 Data preprocessing is an essential step in data science workflow that involves transforming raw data into a format suitable for analysis and machine learning  
 __step 1__: import the header files that are needed for data preprocessing and then  collect the dataset from online in which data preprocessing have to be applied .  
     
      > import pandas as pd   
        import numpy as np  
        from sklearn.impute import SimpleImputer   
        from sklearn.preprocessing import OneHotEncoder  
        from sklearn.preprocessing import MinMaxScaler,StandardScaler
        
 __step2__:  load the dataset  
           dataset=pd.read_csv('Data.csv')  
           find the columns which has missing values.   
           
           >missing_values=dataset.isnull().sum()
           print(missing_values[missing_values>0]).    
           
 __step3__: This step involves  handling the missing values ...means for numerical column we can use  SimpleImputer which will convert the missing values (NaN) with mean

 
            > imputer=SimpleImputer(strategy= 'mean ')  
             dataset[['Age','Salary']]=imputer.fit_transform(dataset[['Age','Salary']]). 

            ##for handling categorical data we will use OneHotEncoder method  
            this method converts each category into a binary vector where only one element is 1 and rest are 0  
            
            categorical_col=['Country','Purchased']  
            encoder=OneHotEncoder( sparse_output=False ,drop='first')  
           encoded_feature=encoder.fit_transform(dataset[categorical_col])   
           encoded_feature_names=encoder.get_feature_names_out(categorical_col)  
           encoded_df=pd.DataFrame(encoded_feature,columns=encoded_feature_names)  
           dataset=dataset.drop(categorical_col,axis=1)  
           dataset=pd.concat([dataset,encoded_df],axis=1).  
__step4__: this step involves scaling -to adjust the range of features using Standarisation or Normalization   we will use Normalization for performing scaling

          >min_max_scaler=MinMaxScaler()
           numerical_cols=['Age','Salary','Country_Antartica','Country_China','Country_India','Country_Indonesia','Country_Sri lanka','Country_nan','Purchased_Yes','Purchased_nan']
            scaled_feature= min_max_scaler.fit_transform(dataset[numerical_cols])
            scaled_df=pd.DataFrame(scaled_feature,columns=numerical_cols)
            dataset[numerical_cols]=scaled_df

      

        
           
![Screenshot 2024-07-28 120712](https://github.com/user-attachments/assets/5d06e4b4-21e8-49c2-8a6f-29f8be541ce5)

![Screenshot 2024-07-28 120757](https://github.com/user-attachments/assets/fab4f8b5-ecf8-4193-ada2-d2fbd108373a)

