# Ex:05 Feature Generation

## AIM
To read the given data and perform Feature Generation process and save the data to a file.

## Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

## ALGORITHM
### STEP 1
Read the given Data

### STEP 2
Clean the Data Set using Data Cleaning Process

### STEP 3
Apply Feature Generation techniques to all the feature of the data set

### STEP 4
Save the data to the file

## CODE
### Developed by : PRANEET S
### Register number : 212221230078
## Data:
```
import pandas as pd
df=pd.read_csv("data.csv")
print(df)

import category_encoders as ce
be=ce.BinaryEncoder()
df1=be.fit_transform(df["bin_1"])
df["bin_1"] = be.fit_transform(df["bin_1"])
df1

be=ce.BinaryEncoder()
df2=be.fit_transform(df["bin_2"])
df["bin_2"] = be.fit_transform(df["bin_2"])
df2

df1=df.copy()

from sklearn.preprocessing import LabelEncoder,OrdinalEncoder,OneHotEncoder
import category_encoders as ce
be=ce.BinaryEncoder()
ohe=OneHotEncoder(sparse=False)
le=LabelEncoder()
oe=OrdinalEncoder()

df1["City"] = ohe.fit_transform(df1[["City"]])
temp=['Cold','Warm','Hot','Very Hot']
oe1=OrdinalEncoder(categories=[temp])
df1['Ord_1'] = oe1.fit_transform(df1[["Ord_1"]])
edu=['High School','Diploma','Bachelors','Masters','PhD']
oe2=OrdinalEncoder(categories=[edu])
df1['Ord_2']= oe2.fit_transform(df1[["Ord_2"]])
df1
```

## Scaling:
```
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
df2=pd.DataFrame(sc.fit_transform(df1),columns=(['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target']))
df2

from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
df3=pd.DataFrame(sc1.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df3

from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
df4=pd.DataFrame(sc2.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df4

from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
df5=pd.DataFrame(sc3.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df5
```

## Encoding Data:
```
import pandas as pd
df=pd.read_csv("Encoding Data.csv")
df
```

## Generation:
```
import category_encoders as ce
be=ce.BinaryEncoder()
ndf=be.fit_transform(df["bin_1"])
df["bin_1"] = be.fit_transform(df["bin_1"])
ndf

be=ce.BinaryEncoder()
ndf2=be.fit_transform(df["bin_2"])
df["bin_2"] = be.fit_transform(df["bin_2"])
ndf2

df1=df.copy()

from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
le=LabelEncoder()
oe=OrdinalEncoder()

df1["nom_0"] = oe.fit_transform(df1[["nom_0"]])
temp=['Cold','Warm','Hot']
oe2=OrdinalEncoder(categories=[temp])
df1['ord_2'] = oe2.fit_transform(df1[['ord_2']])
df1
```

## Scaling:
```
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
df0=pd.DataFrame(sc.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df0

from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
df2=pd.DataFrame(sc1.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df2

from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
df3=pd.DataFrame(sc2.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df3

from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
df4=pd.DataFrame(sc3.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df4
```

## OUTPUT
### Data CSV:

![image](https://github.com/Praneet002/ODD2023-Datascience-Ex-05/assets/94308200/682a5c66-edef-4c1f-a277-4399848774ee)

![image](https://github.com/Praneet002/ODD2023-Datascience-Ex-05/assets/94308200/577349d0-f4dc-46f0-8c65-838f13fae59e)

![image](https://github.com/Praneet002/ODD2023-Datascience-Ex-05/assets/94308200/67e2b2a2-a58a-4423-a159-93b6dee4bce4)

![image](https://github.com/Praneet002/ODD2023-Datascience-Ex-05/assets/94308200/cc2fe42d-a73b-4c43-b269-5b9f4b169a13)

### MinMaxScaling:

![image](https://github.com/Praneet002/ODD2023-Datascience-Ex-05/assets/94308200/6c14365b-822a-4789-9aff-405f19ed2db8)

### Standard Scaling:

![image](https://github.com/Praneet002/ODD2023-Datascience-Ex-05/assets/94308200/4a6a2956-1e12-483e-a124-b7cccff5ffe5)

### MaxAbs Scaling:

![image](https://github.com/Praneet002/ODD2023-Datascience-Ex-05/assets/94308200/bfa26899-a241-4739-9412-0b59672f2630)

### Robust Scaling:

![image](https://github.com/Praneet002/ODD2023-Datascience-Ex-05/assets/94308200/179fc7b8-e565-44f3-b8cd-da6c461dc030)

### Encoding Data CSV:

![image](https://github.com/Praneet002/ODD2023-Datascience-Ex-05/assets/94308200/8dea921f-a04a-479d-b7ff-84f1d919e096)

### MinMaxScaler:

![image](https://github.com/Praneet002/ODD2023-Datascience-Ex-05/assets/94308200/87edc980-0889-4001-b11b-2b60a2898c2e)

### Standard Scaler:

![image](https://github.com/Praneet002/ODD2023-Datascience-Ex-05/assets/94308200/e879fc87-57a7-4a16-a94e-96efc182100a)

### MaxAbsScaler:

![image](https://github.com/Praneet002/ODD2023-Datascience-Ex-05/assets/94308200/364bc05c-a3b4-4eb0-87dd-f04100741d1d)

### Robust Scaler:

![image](https://github.com/Praneet002/ODD2023-Datascience-Ex-05/assets/94308200/1f4f242f-346e-4779-b27d-1ab998a541f5)

## Result:
Thus the Feature Generation and Feature Scaling process is applied to the given data set.
