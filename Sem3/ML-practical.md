# Simple Linear Regression

```py
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.linear_model import LinearRegression

data = pd.read_csv('https://raw.githubusercontent.com/apratim777/apratim777/refs/heads/master/homeprices.csv')
data.head()

x = data.drop('price',axis=1)
x.head()

y = data.price
y.head()

plt.xlabel('Area')
plt.ylabel('Price')
plt.scatter(x,y)

model = LinearRegression()
model.fit(x,y)

model.score(x,y)
```

# Multiple Linear Regression ()

```py
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.linear_model import LinearRegression

data = pd.read_csv('https://raw.githubusercontent.com/apratim777/apratim777/refs/heads/master/homeprices1.csv')
data.head()

mid = data.bedrooms.median()
mid

data.bedrooms = data.bedrooms.fillna(mid)
data

x = data.drop('price',axis=1)
x.head()

y = data.price
y.head()

model = LinearRegression()
model.fit(x,y)

model.score(x,y)

plt.scatter(x.area,y)
```

# Polynomial Linear Regression

```py
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.preprocessing import PolynomialFeatures
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split

data = pd.read_csv('https://raw.githubusercontent.com/apratim777/apratim777/refs/heads/master/Position_Salaries.csv')
data.head()

x = data.drop(['Position','Salary'],axis=1)
x.head()

y = data.Salary
y.head()

train_x,test_x,train_y,test_y = train_test_split(x,y,train_size=0.8)

lin = LinearRegression()
lin.fit(x,y)

poly = PolynomialFeatures(degree=4)
x_poly = poly.fit_transform(x)

pol = LinearRegression()
pol.fit(x_poly,y)

lin.score(x,y)

pol.score(x_poly,y)
```

# Logistic Regression

```py
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import train_test_split

data = pd.read_csv('https://raw.githubusercontent.com/apratim777/apratim777/refs/heads/master/insurance_data.csv')
data.head()

x = data.drop('bought_insurance', axis=1)
x.head()

y = data.bought_insurance
y.head()

plt.scatter(x,y)

train_x,test_x,train_y,test_y = train_test_split(x,y,train_size=0.8)

model = LogisticRegression()
model.fit(train_x,train_y)

model.score(test_x,test_y)

model.predict([[39]])
```

# Multiple Logistic Regression (digit classification)

```py
from sklearn.datasets import load_digits
import matplotlib.pyplot as plt

digits = load_digits()

dir(digits)

plt.gray()
for i in range(2):
    plt.matshow(digits.images[i])

from sklearn.model_selection import train_test_split

train_x,test_x,train_y,test_y = train_test_split(digits.data, digits.target, train_size = 0.8)
train_y

from sklearn import linear_model
model = linear_model.LogisticRegression()

model.fit(train_x,train_y)

model.score(test_x, test_y)

model.predict(digits.data[[104]])

plt.matshow(digits.images[100])
```

# Decision Tree Algo

```py
import pandas as pd

df=pd.read_csv("https://raw.githubusercontent.com/apratim777/apratim777/master/salaries.csv")
df.head()

inputs=df.drop('salary_more_then_100k',axis='columns')
inputs

target=df['salary_more_then_100k']
target

from sklearn.preprocessing import LabelEncoder
le_company=LabelEncoder()
le_job=LabelEncoder()
le_degree=LabelEncoder()

inputs['company_name']=le_company.fit_transform(inputs['company'])
inputs['job_name']=le_job.fit_transform (inputs['job'])
inputs['degree_name']=le_degree.fit_transform(inputs['degree'])
inputs

inputs_n=inputs.drop(['company','job','degree'],axis='columns')
inputs_n

target

from sklearn import tree
model=tree.DecisionTreeClassifier()

model.fit(inputs_n,target)

model.score(inputs_n,target)

model.predict([[2,1,1]])
```

# ANN - Digit Classification

```py
import tensorflow as tf
from tensorflow import keras
import matplotlib.pyplot as plt
#%matplotlib inline
import numpy as np

(x_train, y_train),(x_test, y_test)= keras.datasets.mnist.load_data()

len(x_test)

len(y_test)

len(x_train)

len(y_train)

x_train[0].shape

x_train[1]
y_train[7]

x_train[0]

plt.matshow(x_train[1000])

y_train[0]

x_train=x_train/255
x_test=x_test/255

x_train[0]

x_train_flattened=x_train.reshape(len(x_train),28*28)
x_test_flattened=x_test.reshape(len(x_test),28*28)

x_train_flattened.shape

x_train_flattened[0]

Very simple neural network with no hidden layers(22.08.24)

from tensorflow import keras

model=keras.Sequential([
        keras.layers.Dense(10,input_shape=(784,),activation='sigmoid')
])
model.compile(optimizer='adam',
              loss='sparse_categorical_crossentropy',
              metrics=['accuracy'])
model.fit(x_train_flattened,y_train,epochs=5)


model.evaluate(x_test_flattened,y_test)

Using Hidden Layer

model=keras.Sequential([
    keras.layers.Dense(100,input_shape=(784,),activation='relu'),
    keras.layers.Dense(50,input_shape=(784,),activation='sigmoid'),
    keras.layers.Dense(10,activation='sigmoid')

])
model.compile(optimizer='adam',
              loss='sparse_categorical_crossentropy',
              metrics=['accuracy'])
model.fit(x_train_flattened,y_train,epochs=5)

y_predicted=model.predict(x_test_flattened)
y_predicted[0]

np.argmax(y_predicted[0])

plt.matshow(x_test[4])

np.argmax(y_predicted[4])

y_predicted_labels=[np.argmax(i) for i in y_predicted]

cm=tf.math.confusion_matrix(labels=y_test,predictions=y_predicted_labels)
cm

import seaborn as sn
plt.figure(figsize=(10,7))
sn.heatmap(cm,annot=True,fmt='d')
plt.xlabel('Predicted')
plt.ylabel('Truth')

Small image classification


import tensorflow as tf
from tensorflow.keras import datasets,layers,models
import matplotlib.pyplot as plt
import numpy as np

(x_train, y_train), (x_test, y_test) = datasets.cifar10.load_data()
x_train.shape

y_train.shape

y_train[:5]

y_train=y_train.reshape(-1,)
y_train = y_train.flatten()
y_train[:5]

y_test = y_test.reshape(-1)

classes=["airplane","automobile","bird","cat","deer","dog","frog","horse","ship","truck"]

def plot_sample(x,y,index):
    plt.figure(figsize=(15,2))
    plt.imshow(x[index])
    plt.xlabel(classes[y[index]])

plot_sample(x_train,y_train,30)
```

# CNN - cifar10 dataset

```py
import tensorflow as tf
from tensorflow.keras import datasets, layers, models
import matplotlib.pyplot as plt
import numpy as np


(X_train, y_train), (X_test,y_test) = datasets.cifar10.load_data()
X_train.shape

X_test.shape

y_train.shape

y_train[:5]


#y_train = y_train.reshape(-1,)
y_train = y_train.flatten()
y_train[:5]

y_test = y_test.reshape(-1,)

classes = ["airplane","automobile","bird","cat","deer","dog","frog","horse","ship","truck"]


def plot_sample(X, y, index):
    plt.figure(figsize = (15,2))
    plt.imshow(X[index])
    plt.xlabel(classes[y[index]])

plot_sample(X_train, y_train, 0)

plot_sample(X_train, y_train, 1)


X_train = X_train / 255.0
X_test = X_test / 255.0


ann = models.Sequential([
        layers.Flatten(input_shape=(32,32,3)),
        layers.Dense(3000, activation='relu'),
        layers.Dense(1000, activation='relu'),
        layers.Dense(10, activation='sigmoid')
    ])

ann.compile(optimizer='SGD',
              loss='sparse_categorical_crossentropy',
              metrics=['accuracy'])

ann.fit(X_train, y_train, epochs=3)

# -----

from sklearn.metrics import confusion_matrix , classification_report
import numpy as np
y_pred = ann.predict(X_test)
y_pred_classes = [np.argmax(element) for element in y_pred]

print("Classification Report: \n", classification_report(y_test, y_pred_classes))


cnn = models.Sequential([
    layers.Conv2D(filters=32, kernel_size=(3, 3), activation='relu', input_shape=(32, 32, 3)),
    layers.MaxPooling2D((2, 2)),

    layers.Conv2D(filters=64, kernel_size=(3, 3), activation='relu'),
    layers.MaxPooling2D((2, 2)),

    layers.Flatten(),
    layers.Dense(64, activation='relu'),
    layers.Dense(10, activation='softmax')
])

cnn.compile(optimizer='adam',
              loss='sparse_categorical_crossentropy',
              metrics=['accuracy'])

cnn.fit(X_train, y_train, epochs=5)


cnn.evaluate(X_test,y_test)

y_pred = cnn.predict(X_test)
y_pred[:5]

y_classes = [np.argmax(element) for element in y_pred]
y_classes[:5]

y_test[:5]

plot_sample(X_test, y_test,3)

classes[y_classes[3]]

classes[y_classes[3]]
```