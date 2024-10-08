# Developing a Neural Network Regression Model

## AIM

To develop a neural network regression model for the given dataset.

## THEORY

Neural networks consist of simple input/output units called neurons. In this article, we will see how neural networks can be applied to regression problems.

Regression helps in establishing a relationship between a dependent variable and one or more independent variables. Although neural networks are complex and computationally expensive, they are flexible and can dynamically pick the best type of regression, and if that is not enough, hidden layers can be added to improve prediction.

Build your training and test set from the dataset, here we are making the neural network 2 hidden layer with activation layer as relu and with their nodes in them. Now we will fit our dataset and then predict the value.

## Neural Network Model :

![nn](https://github.com/user-attachments/assets/d987cb5e-33a8-4c5c-9780-536df84b1d95)



## DESIGN STEPS

### STEP 1:
Loading the dataset

### STEP 2:
Split the dataset into training and testing

### STEP 3:
Create MinMaxScalar objects ,fit the model and transform the data.

### STEP 4:
Build the Neural Network Model and compile the model.

### STEP 5:
Train the model with the training data.

### STEP 6:
Plot the performance plot

### STEP 7:
Evaluate the model with the testing data.

## PROGRAM

### Name: Thirugnanamoorthi G
### Register Number: 212221230117
```

import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import MinMaxScaler
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense
from google.colab import auth
import gspread
from google.auth import default

auth.authenticate_user()
creds,_=default()
gc=gspread.authorize(creds)
worksheet=gc.open('newdata').sheet1
data=worksheet.get_all_values()
dataset1=pd.DataFrame(data[1:],columns=data[0])
dataset1=dataset1.astype(int)

x = df[['Input ']].values
y = df[['Output']].values

x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.33,random_state=33)
Scaler=MinMaxScaler()
Scaler.fit(x_train)
x_train=Scaler.transform(x_train)
ai_brain=Sequential([
    Dense(8,activation='relu'),
    Dense(10,activation='relu'),
    Dense(1)
])
ai_brain.compile(optimizer='rmsprop',loss='mse')
ai_brain.fit(x_train,y_train,epochs=100)

loss_df=pd.DataFrame(ai_brain.history.history)
loss_df.plot()
X_test1 = Scaler.transform(x_test)  
ai_brain.evaluate(X_test1, y_test)
X_n1 = [[3], [5]]

X_n1_1 = Scaler.transform(X_n1)
ai_brain.predict(X_n1_1)


```
## Dataset Information


![1](https://github.com/user-attachments/assets/75e308b2-f3f6-4e74-967a-142d2f5776ba)

## OUTPUT

## Training Loss Vs Iteration Plot

![3](https://github.com/user-attachments/assets/689a9b4d-50e4-4e0c-9e39-7f64713759cf)


## Test Data Root Mean Squared Error

![4](https://github.com/user-attachments/assets/f6a7c032-c2db-4a1f-9979-acf67afc3757)


## New Sample Data Prediction

![5](https://github.com/user-attachments/assets/a3a1c117-de8f-47be-a310-4c033455e1ae)


## RESULT

Thus to develop a neural network regression model for the dataset created is successfully executed.
