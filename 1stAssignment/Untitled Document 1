import numpy as np
import matplotlib.pyplot as plt
import pandas as pnd
import seaborn as sns

relevant_features = ["age", "sex", "cp", "trestbps", "chol", "fbs", "restecg", "thalach", "exang", "oldpeak", "slope", "ca", "thal", "diagnosis"]
data = pnd.read_csv("processed.cleveland.csv", names=relevant_features)

data.drop(data[data["ca"] == '?'].index, inplace=True)
data.drop(data[data["thal"] == '?'].index, inplace=True)
data = data.astype('float64') 

data_n = data.values

X = data_n[:,:-1]
y = data_n[:,-1]

#X.shape = (297,13)
y = y.reshape(X.shape[0],1)
#y.shape = (297,1)

m = X.shape[0]

diag0 = (y==0)
diag1 = (y==1)
diag2 = (y==2)
diag3 = (y==3)

plt.scatter(X[diag0[:,0],0],X[diag0[:,0],1],c='#1f77b4',marker="+")
plt.scatter(X[diag1[:,0],0],X[diag1[:,0],1],c="#ff7f0e",marker="o")
plt.scatter(X[diag2[:,0],0],X[diag2[:,0],1],c="#2ca02c",marker="x")
plt.scatter(X[diag3[:,0],0],X[diag3[:,0],1],c="#d62728",marker="d")
plt.xticks(np.arange(25, 80, 10))
plt.yticks(np.arange(0, 2, 1))
plt.xlabel("Ages")
plt.ylabel("Sex")
plt.legend(["Diagnosis 0", "Diagnosis 1", "Diagnosis 2", "Diagnosis 3"])
