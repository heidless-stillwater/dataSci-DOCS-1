# markdown maths cheatsheet
### [Cheat Sheet: Adding Math Notation to Markdown](https://www.upyesp.org/posts/makrdown-vscode-math-notation/#:~:text=Including%20Math%20Notation%20in%20Markdown&text=Inline%20math%20notation%20is%20wrapped,signs%2C%20wrapped%20inside%20triple%20backticks.)

# account & doc
```
ACCOUNT: heidlessemail09@gmail.com

Google Group Name: 'ai_mc'

# conda
source ~/miniconda3/bin/activate ml_datasci

# project`

/home/heidless/projects/heidless-python/dataSci-APPS-2/sandbox/datasci/

/home/heidless/projects/heidless-python/dataSci-APPS-2/sandbox/datasci/

AIMegaCourse

[ai-megaCourse](https://github.com/heidless-stillwater/ai-megaCourse)

```



## [Python Numpy Tutorial (with Jupyter and Colab)](https://cs231n.github.io/python-numpy-tutorial/)

## [tech with tim: machine learning](https://www.techwithtim.net/tutorials/machine-learning-python)
- ### Resources
  - [YouTube: Python Machine Learning & AI Mega Course - Learn 4 Different Areas of ML & AI](https://www.youtube.com/watch?v=WFr2WgN9_xE&t=217s)
  - [GIT: ai-megaCourse](https://github.com/heidless-stillwater/ai-megaCourse)
  - [DATASETS: UC Irvine Machine Learning Repository](https://archive.ics.uci.edu/)
    - [Student Performance
](https://archive.ics.uci.edu/dataset/320/student+performance)
    - [Car Evaluation Dataset](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbmdXUTdHWl90X1gtS09UVk16OXZCazdIaU1jd3xBQ3Jtc0tsZUQxeFBaR0pqRDdMNzMwWHBnOHdSay1rT2lkUE56SnYxbXE0eTdVYVVnOWE1NG50OGpIcmJZdzNZRkFiTGlsbzVCOTNOOUZSUEhkWW9vTk1HN2U4ZUZ0VloyOGJKM1V6bUdmbDRTQU5QVlZOaWV2TQ&q=https%3A%2F%2Fdev-cms.us-east-1.linodeobjects.com%2FCar_Data_Set_1bd53a190c.zip&v=WFr2WgN9_xE)

## env
```
pip install -U PyQt5
pip install -U matplotlib
pip install -U pandas
pip install -U numpy
pip install -U scikit-learn
pip install -U icecream
pip install -U logging
pip install -U streamlit

```

# Table of contents
1. [Introduction](#introduction)
2. [Some paragraph](#paragraph1)
    1. [Sub paragraph](#subparagraph1)
3. [Another paragraph](#paragraph2)
   

## [01-linear-regression](https://www.techwithtim.net/tutorials/machine-learning-python/linear-regression)

$$
y = mx + b\\
m: \ slope\\
b: \ intercept \\  

$$

$$
slope = m = \frac{y_2 - y_1}{x_2 - x_1}
  
$$

### Save Model
```
linear.fit(x_train, y_train)
acc = linear.score(x_test, y_test)
log_this(acc, "acc")

f_name = "studentmodel.pickle"

# write
with open(f_name, "wb") as f:
    pickle.dump(linear, f) 

# load
pickle_in = opem(f_name, "rb")


```

## [02-nearest-neighbor (KNN)](https://www.techwithtim.net/tutorials/machine-learning-python/k-nearest-neighbors-1)
- ### [scikit-learn: KNeighborsClassifier](https://scikit-learn.org/dev/modules/generated/sklearn.neighbors.KNeighborsClassifier.html)
- ### [K-Nearest Neighbor(KNN) Algorithm](https://www.geeksforgeeks.org/k-nearest-neighbours/)

### Classification algorithm

The K-Nearest Neighbors (KNN) algorithm is a supervised machine learning method employed to tackle classification and regression problems.

The K-Nearest Neighbors (KNN) algorithm is a supervised machine learning method employed to tackle classification and regression problems.

### Why do we need a KNN algorithm?
(K-NN) algorithm is a versatile and widely used machine learning algorithm that is primarily used for its simplicity and ease of implementation. It does not require any assumptions about the underlying data distribution. It can also handle both numerical and categorical data, making it a flexible choice for various types of datasets in classification and regression tasks. It is a non-parametric method that makes predictions based on the similarity of data points in a given dataset. K-NN is less sensitive to outliers compared to other algorithms.

The K-NN algorithm works by finding the K nearest neighbors to a given data point based on a distance metric, such as Euclidean distance. The class or value of the data point is then determined by the majority vote or average of the K neighbors. This approach allows the algorithm to adapt to different patterns and make predictions based on the local structure of the data.

### Distance Metrics Used in KNN Algorithm

$$
k:\ (HyperParameter)\ the\ amount\ of\ neighbors\ we're\ going\ to\ look\ for \\

m: magnitude \\
d: distance
$$
i.e. k=3 : look for the 3 nearest datapoints

#### Euclidean Distance
This is nothing but the cartesian distance between the two points which are in the plane/hyperplane. 

Euclidean distance can also be visualized as the length of the straight line that joins the two points which are into consideration. 

This metric helps us calculate the net displacement done between the two states of an object.

$$
Euclidean\ Distance:\  
m = d = \sqrt{(X_2-X_1)^2 + (y_2 - y_1)^2}\\
$$

#### Manhattan Distance
Manhattan Distance metric is generally used when we are interested in the total distance traveled by the object instead of the displacement. 

This metric is calculated by summing the absolute difference between the coordinates of the points in n-dimensions.

$$
    d(x,y) = \sum_{i=1}^n|x_i - y_i|
$$

### limitations
Computationally expensive (storage, processing, time). Needs to consider each & every datapoint(distance) when we attempy to make a prediction.

## [03-Support Vector Machines (SVM)](https://www.techwithtim.net/tutorials/machine-learning-python/svm-1)
- ### [DataSets: UC Irvine Machine Learning Repository](https://archive.ics.uci.edu/)
  - #### [Breast Cancer Wisconsin (Diagnostic)](https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic)
- ### [scikit-learn: Support Vector Machines](https://scikit-learn.org/dev/modules/svm.html)

$$
f(X_1, X2) => X_3
$$

SVM stands for a support vector machine. 

SVM's are typically used for classification tasks similar to what we did with K Nearest Neighbors. 

They work very well for high dimensional data and are allow for us to classify data that does not have a linear correspondence.

Algorithm attempts to identify the optimal hyper-plane within the data set.
- find the hyper-plane which is the same distance from the two closest points of each opposite class

**Support vector machines (SVMs)** are a set of supervised learning methods used for 
- classification, 
- regression and 
- outliers detection.

#### The advantages of support vector machines are:
- Effective in high dimensional spaces.
- Still effective in cases where number of dimensions is greater than the number of samples.
- Uses a subset of training points in the decision function (called **support vectors**), so it is also memory efficient.
- Versatile: different Kernel functions can be specified for the decision function. Common kernels are provided, but it is also possible to specify custom kernels.

#### The disadvantages of support vector machines include:
- If the number of features is much greater than the number of samples, avoid over-fitting in choosing Kernel functions and regularization term is crucial.
- SVMs do not directly provide probability estimates, these are calculated using an expensive five-fold cross-validation (see Scores and probabilities, below).

**Kernel Function** is a method used to take data as input and transform it into the required form of processing data. 

“**Kernel**” is used due to a set of mathematical functions used in Support Vector Machine providing the window to manipulate the data. 

So, Kernel Function generally transforms the training set of data so that a non-linear decision surface is able to transform to a linear equation in a higher number of dimension spaces. 


## [04-K-Means Clustering](https://www.techwithtim.net/tutorials/machine-learning-python/k-means-1)
- ### [demo: K-Means clustering on the handwritten digits data](https://scikit-learn.org/stable/auto_examples/cluster/plot_kmeans_digits.html)
- ### [sci-kit: KMeans](https://scikit-learn.org/1.5/modules/generated/sklearn.cluster.KMeans.html)

**K-Means Clustering** is an unsupervised learning algorithm that attempts to divide our training data into k unique clusters to classify information. 

This means this algorithm does not require labels for given test data. It is responsible for learning the differences between our data points and determine what features determining what class.

#### Supervised vs Unsupervised Algorithm
Supervised learning means that when we pass training data to our algorithm we also pass the estimated values or classes for each of those data points. 

If we were using an **unsupervised** algorithm we would only pass the features and omit the class.

#### How K-Means Clustering Works
The **K-Means clustering** algorithm is a classification algorithm that follows the steps outlined below to cluster data points together. 

It attempts to separate each area of our high dimensional space into sections that represent each class. 

When we are using it to predict it will simply find what section our point is in and assign it to that class.

#### steps:
- Step 1: Randomly pick K points to place K centroids 
- Step 2: Assign all of the data points to the centroids by distance. The closest centroid to a point is the one it is assigned to. 
- Step 3: Average all of the points belonging to each centroid to find the middle of those clusters (center of mass). Place the corresponding centroids into that position. 
- Step 4: Reassign every point once again to the closest centroid. 
- Step 5: Repeat steps 3-4 until no point changes which centroid it belongs to.


## [05-neural-networks]()
