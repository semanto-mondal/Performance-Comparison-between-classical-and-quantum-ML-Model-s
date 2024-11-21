# Performance-Comparison-between-classical-and-quantum-ML-Models
## Binary Classification using Mushroom Dataset: Performance Comparison between Classical and Quantum ML Model’s


**GROUP COMPOSITION:**


*   Md. Ekhtear Ahammed
*   Rajib Chandra Ghosh
*   Semanto Mondal
*  Alberto Moccardi

NOTE: The Notebook is prepared for participating in the [UNINA QISKIT COMPETITION](https://www.unina.it/-/63454289-qiskit-fall-fest-2024)

## Introduction 

Artificial Intelligence is the parent class of Machine Learning and Deep Learning. Nowadays we can see a huge enhancement in the field of AI. Due to the enormous hardware capacity such as GPUs, HPC (high-performance computing), and Parallel and Distributed computing, we are now able to perform several operations which could not have been thought of just a few years ago. But still, these computation powers are not enough for a lot of problems. Also, there are many problems which cannot be solved or formulated using classical computers. Here comes quantum computing having acute capabilities to solve many problems more efficiently. Here we have tried to perform a simple binary classification of a mushroom dataset where we must predict whether a mushroom is edible or not. This dataset is a clean version of the original Mushroom Dataset for Binary Classification Available at UCI Library. It contains 9 columns. The Target Class contains two values - 0 or 1 - where 0 refers to edible and 1 refers to poisonous.

# Dataset Description

This dataset is a cleaned version of the original Mushroom Dataset for Binary Classification Available at UCI Library. This dataset was cleaned using various techniques such as Modal imputation, one-hot encoding, z-score normalization, and feature selection. It contains 9 columns:

*  Cap Diameter
*  Cap Shape
* Gill Attachment
* Gill Color
* Stem Height
* Stem Width
* Stem Color
* Season
* Target Class - Is it edible or not?

The Target Class contains two values - 0 or 1 - where 0 refers to edible and 1 refers to poisonous.


**More Information can be achieved about the dataset from the below link:
[Mushroom Dataset](https://archive.ics.uci.edu/dataset/848/secondary+mushroom+dataset)**


## Plan of Attack 
We have performed the following tasks:

* Loading the dataset and performing necessary preprocessing

* Considering a subset of the original dataset and making a balanced dataset to make the computation simpler

* Selecting Important features using several feature selection techniques

* Training Classical ML Models (Random Forest, SVM) and Quantum ML Models

* Testing the model's performance on the test dataset

* Comparing the performance of classical ML models and Quantum ML Models in terms of accuracy and computation time

## Model Development 
We have considered two different types of models. One is classical machine learning models on the contrary others are quantum machine learning models. The diagram below shows the high-level workflow (building blocks) diagram of both types of models. Initial steps such as normalization, preprocessing, and splitting datasets are the same for both.

![Workflow AMber (2)](https://github.com/user-attachments/assets/ec7e676b-867a-4a3b-aa02-7a5c1b6e4da8)
FIG: Classical ML Models
![Workflow AMber (3)](https://github.com/user-attachments/assets/ae37bbcb-ce73-4976-b24b-d40d8a6e8d5a)
FIG: QML Models

## Results Comparision 

The plot below shows the accuracy obtained on the same test set and the total training time required to train each of the models. To make QNN and ANN comparable we have considered a number of hidden layers = reps of the ansatz circuit even though the iteration is different. We compared the computation time just to visualize how much time they took to acquire the accuracy obtained on the test set. From the comparison below we can conclude that, due to robustness and optimization ANN and RF (random forest) outperform the QML models. On the contrary Quantum PCA, VQC outperforms SVC and LR. Due to hardware noise and other additional factors, we are getting less accuracy in some of the QML but still at the beginning stage, it’s well enough and can perform better in some specific cases such as high-dimensional data. We can also see from the below plot that Quantum PCA performs significantly better in terms of separation among classes in high dimensional space using quantum kernels. Hence, it’s clear that quantum computing can influence AI related tasks significantly soon and can solve many more problems which are not so efficient using classical computers.

![image](https://github.com/user-attachments/assets/dc5aba20-7c96-49b7-8f12-e5206e45d083)
FIG: Quantum PCA vs Classical Kernal PCA Decision Boundary 

![newplot (1)](https://github.com/user-attachments/assets/3a9226ba-62f4-4340-bf5f-3993aee8f070)
FIG: Performance Comparison among different models w.r.t time and accuracy

## Model Comparison

The table below summarizes the accuracy and computation time of various models:

| Model                  | Accuracy | Computation Time (seconds) |
|------------------------|----------|----------------------------|
| SVC                    | 0.57     | 64                         |
| QSVC                   | 0.60     | 512                        |
| RF                     | 0.73     | 2                          |
| VQC                    | 0.65     | 352                        |
| QNN                    | 0.53     | 600                        |
| ANN                    | 0.69     | 15                         |
| LR with Kernel PCA     | 0.62     | 1800                       |
| LR with Quantum PCA    | 0.61     | 120                        |





