Developed by: Thanushree M

RegisterNumber:  212224240169


# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary libraries.
2. Read the dataset and separate the independent and dependent variables.
3. Split the dataset into training and testing.
4. Do preprocessing if needed, in this case vectorization is needed which is done using CountVectorizer()
5. Train the model using SVC() algorithm and .fit()
6. Predict the model on x_test.
7. Measure its accuracy

## Program:
Program to implement the SVM For Spam Mail Detection..
```
        import pandas as pd
        data=pd.read_csv("/content/spam.csv",encoding="Windows-1252")
        data.info()
        
        x=data['v2'].values
        y=data['v1'].values
        x.shape
        y.shape
        
        from sklearn.model_selection import train_test_split
        x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)
        
        from sklearn.feature_extraction.text import CountVectorizer
        cv=CountVectorizer()
        x_train=cv.fit_transform(x_train)
        x_test=cv.transform(x_test)
        x_train
        
        from sklearn.svm import SVC
        svc=SVC()
        svc.fit(x_train,y_train)
        y_pred=svc.predict(x_test)
        y_pred
        
        from sklearn.metrics import accuracy_score
        acc=accuracy_score(y_test,y_pred)
        acc
```

## Output:

![image](https://github.com/user-attachments/assets/da91d5b4-7730-475f-951d-007b18f2caae)

![image](https://github.com/user-attachments/assets/f74e8eee-e269-4021-a79f-38e4096e7292)

![image](https://github.com/user-attachments/assets/43520eff-4998-4f91-8b6c-9aa27c34c842)

![image](https://github.com/user-attachments/assets/b7675b9a-fc39-48d5-9690-7f2689097140)

![image](https://github.com/user-attachments/assets/671071e8-1e03-4965-9d71-a7c9b8faeee3)



## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
