# Ex:05 Feature Generation

# AIM
To read the given data and perform Feature Generation process and save the data to a file.

# Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature Generation techniques to all the feature of the data set
#### STEP 4
Save the data to the file

# PROGRAM
```python
### For Encoding.csv file

import pandas as pd
df=pd.read_csv('Encoding Data.csv')
df.head()
df['ord_2'].unique()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot']
en= OrdinalEncoder(categories = [climate])
df['ord_2']=en.fit_transform(df[["ord_2"]])
df
le = LabelEncoder()
df['Nom_0'] = le.fit_transform(df[["nom_0"]])
df
!pip install --upgrade category_encoders
from category_encoders import BinaryEncoder
be = BinaryEncoder()
data = be.fit_transform(df['bin_1'])
df  = pd.concat([df,data],axis=1)
df
be = BinaryEncoder()
data = be.fit_transform(df['bin_2'])
df  = pd.concat([df,data],axis=1)
df
```
### Data.csv
```python
import pandas as pd
df1 = pd.read_csv("data.csv")
df1.head()
df1['Ord_1'].unique()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot','Very Hot']
en= OrdinalEncoder(categories = [climate])
df1['Ord_1']=en.fit_transform(df1[["Ord_1"]])
df1
df1['Ord_2'].unique()
cl = ['High School','Diploma','Bachelors','Masters','PhD']
en= OrdinalEncoder(categories = [cl])
df1['Ord_2']=en.fit_transform(df1[["Ord_2"]])
df1
le = LabelEncoder()
df1['City'] = le.fit_transform(df1[["City"]])
df1
from category_encoders import BinaryEncoder
be = BinaryEncoder()
dat = be.fit_transform(df1['bin_1'])
df1  = pd.concat([df1,dat],axis=1)
df1
from category_encoders import BinaryEncoder
be = BinaryEncoder()
data1 = be.fit_transform(df1['bin_2'])
df1  = pd.concat([df1,data1],axis=1)
df1
```
### BMI.csv file
```python
import pandas as pd
df2 = pd.read_csv("/content/bmi.csv")
df2.head()
be = BinaryEncoder()
data2 = be.fit_transform(df2['Gender'])
df2  = pd.concat([df2,data2],axis=1)
df2
df2 = pd.get_dummies(df2, prefix=['Index'] ,columns=['Index'])
df2
```

# OUTPUT

### For encoding.csv file
#### Initial data:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-05/assets/119393675/f4fe37e3-ba5c-4b95-8d55-91476fe4ac55)

#### Unique value:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-05/assets/119393675/339a8e85-5579-4b62-add2-81ddd5ffb991)


#### Ordinal Encoder:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-05/assets/119393675/5b0836ec-072c-4eb4-88aa-ff07d98f2e51)
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-05/assets/119393675/e803c3f7-a88f-4a55-8f83-d8f3a6af842e)


#### Label Encoder:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-05/assets/119393675/c8eee661-21b0-49f5-926c-c271fe62c332)


#### Binary Encoder:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-05/assets/119393675/e81127c4-e6d3-4b39-a284-3f88ae525aae)
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-05/assets/119393675/cfcce2d7-cfe5-479f-acb6-84daa689cbc9)

### For Data.csv file

#### Initial data:
![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-05/assets/119393675/0ec23774-c2aa-488f-981e-6b93074880b3)

#### Unique value:


![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-05/assets/119393675/9b6dfed0-c23d-4553-a43f-af1aed5bce87)


#### Ordinal Encoder:

![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-05/assets/119393675/c714e4a4-943b-4b0d-a6a5-97883ef6c58c)

![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-05/assets/119393675/2bfced59-1371-41a8-b6cc-df7731ba0935)


#### Label Encoder:

![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-05/assets/119393675/65051665-c5eb-4cec-82bd-bbe0f93a721d)


#### Binary Encoder:

![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-05/assets/119393675/acafeb0d-bc25-4e32-9248-e4db0bc73156)

![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-05/assets/119393675/d406ca2e-fdef-43df-8712-6d0d64038044)

### For bmi.csv file

#### Initial data:

![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-05/assets/119393675/9dcb8853-e71b-4442-8493-3ab51cd4673c)


#### Binary Encoders:

![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-05/assets/119393675/0e692be9-0d3b-4b50-8061-93bc43dbfa00)


#### Dummies:

![image](https://github.com/abinayasangeetha/ODD2023-Datascience-Ex-05/assets/119393675/c22a3106-9968-4dfe-a23d-e4e7e324c419)


# RESULT:
The Feature Generation process was performed and saved the data to a file.
