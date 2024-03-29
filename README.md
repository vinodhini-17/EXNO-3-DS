## EXNO-3-DS

# AIM:
To read the given data and perform Feature Encoding and Transformation process and save the data to a file.

# ALGORITHM:
STEP 1:Read the given Data.
STEP 2:Clean the Data Set using Data Cleaning Process.
STEP 3:Apply Feature Encoding for the feature in the data set.
STEP 4:Apply Feature Transformation for the feature in the data set.
STEP 5:Save the data to the file.

# FEATURE ENCODING:
1. Ordinal Encoding
An ordinal encoding involves mapping each unique label to an integer value. This type of encoding is really only appropriate if there is a known relationship between the categories. This relationship does exist for some of the variables in our dataset, and ideally, this should be harnessed when preparing the data.
2. Label Encoding
Label encoding is a simple and straight forward approach. This converts each value in a categorical column into a numerical value. Each value in a categorical column is called Label.
3. Binary Encoding
Binary encoding converts a category into binary digits. Each binary digit creates one feature column. If there are n unique categories, then binary encoding results in the only log(base 2)ⁿ features.
4. One Hot Encoding
We use this categorical data encoding technique when the features are nominal(do not have any order). In one hot encoding, for each level of a categorical feature, we create a new variable. Each category is mapped with a binary variable containing either 0 or 1. Here, 0 represents the absence, and 1 represents the presence of that category.

# Methods Used for Data Transformation:
  # 1. FUNCTION TRANSFORMATION
• Log Transformation
• Reciprocal Transformation
• Square Root Transformation
• Square Transformation
  # 2. POWER TRANSFORMATION
• Boxcox method
• Yeojohnson method

# CODING AND OUTPUT:
    import pandas as pd
    df=pd.read_csv("/content/Encoding Data (1).csv")
    df
  ![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/40bfb86a-3fac-4076-ab9a-92b557901f7d)
      from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
      pm=['Hot','Warm','Cold']
      e1=OrdinalEncoder(categories=[pm])
      e1.fit_transform(df[["ord_2"]])
  ![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/22d9b38b-f286-4ffc-b8f3-00d1307120cf)
      df['bo2']=e1.fit_transform(df[["ord_2"]])
  ![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/1f7cab4e-b56f-4ea2-ba40-a9dca33fc43c)
       le=LabelEncoder()
       dfc=df.copy()
       dfc['ord_2']=le.fit_transform(dfc['ord_2'])
       ![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/56259ff0-7d1a-441a-8cd2-c8ce1baa8c11)
       from sklearn.preprocessing import OneHotEncoder
       ohe=OneHotEncoder(sparse=False)
       df2=df.copy()
       enc=pd.DataFrame(ohe.fit_transform(df2[['nom_0']]))
       ![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/ed7c92e8-f965-4874-8f25-14d163d45cef)
        df2=pd.concat([df2,enc],axis=1)
        ![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/cf8a255d-6a4a-4801-89d4-68cfa4cae31f)
        ![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/9b709349-79b5-46ad-8c20-500ee0d52645)
         from category_encoders import BinaryEncoder
         df=pd.read_csv("/content/data.csv")
         be=BinaryEncoder()
         nd=be.fit_transform(df['Ord_2'])
         dfb=pd.concat([df,nd],axis=1)
         dfb1=df.copy()
         ![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/59287709-2c34-43a1-a5d5-d8de8c4e2b0e)
         from category_encoders import TargetEncoder
         te=TargetEncoder()
         cc=df.copy()
         new=te.fit_transform(X=cc["City"],y=cc["Target"])
         cc=pd.concat([cc,new],axis=1)
         ![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/af1f6adc-b073-4594-928f-78ff8ae8221a)

         
  ![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/feded1fc-f5df-4aca-b5d0-6abfaa1dcaf4)
          
![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/e315eff9-d85a-4213-bf2f-dc6fa2547ca9)
         
![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/7d326712-5042-4520-a9b8-8b4d12fbcf28)
          
![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/6920b7f0-7d06-4e92-9509-40897ffa8275)
           df["Higly Positive Skew_borcox"],parameters=stats.boxcox(df["Highly Positive Skew"])
           
![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/6574e292-7354-4dd7-9f7e-bd3d12bf5041)

         df["Highly Negative Skew_yeojohnson"],parameters=stats.yeojohnson(df["Highly Negative Skew"])
![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/ccc636e2-c3fe-4487-af52-2409c55e7a8b)
         from sklearn.preprocessing import QuantileTransformer
         qt=QuantileTransformer(output_distribution='normal')
         ![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/0c093f6a-e17c-419b-ad00-474ef18b23fd)
         
 ![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/ff48fe66-1bda-4227-8b1c-7293e1a31443)
         ![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/be97c3b7-697d-461a-870e-258ca03efa87)
         ![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/2c57ea1b-30dc-469d-bc6f-42266eba1cd0)

![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/c3810c1e-034d-47ce-883c-c9c7ecdee05a)
         ![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/36f959b2-3852-4e7e-b227-96799d81806b)
          ![image](https://github.com/vinodhini-17/EXNO-3-DS/assets/145742741/12e65b68-deb5-4a9b-b53b-521170744c5a)


# RESULT:
    
Thus To read the given data and perform Feature Encoding and Transformation process and save the data to a file has successfully executed 

       
