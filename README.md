# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. 
2. 
3. 
4. 

## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: DHANASSHREE M
RegisterNumber:  212221230018
*/
import chardet
file='/content/spam.csv'
with open(file, 'rb') as rawdata:
    result = chardet.detect(rawdata.read(100000))
result

import pandas as pd
df=pd.read_csv("/content/spam.csv",encoding='windows-1252')

df.head()

df.info()

df.isnull().sum()

x=df['v1'].values

y=df['v2'].values

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)

from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()

x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)

from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred

from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```

## Output:
![ex9 ml](https://user-images.githubusercontent.com/94165415/203593494-2d3c4f9a-c1c4-479c-9e71-cee75f5471d1.png)

![mlex9](https://user-images.githubusercontent.com/94165415/203593546-54d54e95-f7fc-4802-b0e5-46ccc8108191.png)



## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
