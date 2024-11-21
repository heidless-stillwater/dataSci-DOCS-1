# markdownn maths cheatsheet
[Cheat Sheet: Adding Math Notation to Markdown](https://www.upyesp.org/posts/makrdown-vscode-math-notation/#:~:text=Including%20Math%20Notation%20in%20Markdown&text=Inline%20math%20notation%20is%20wrapped,signs%2C%20wrapped%20inside%20triple%20backticks.)


# account & doc
```
ACCOUNT: heidlessemail09@gmail.com

Google Group Name: 'ai_mc'

# conda
source ~/miniconda3/bin/activate ml_datasci

# project
[ai-megaCourse](https://github.com/heidless-stillwater/ai-megaCourse)

```

## [Python Numpy Tutorial (with Jupyter and Colab)](https://cs231n.github.io/python-numpy-tutorial/)

## [tech with tim: machine learning](https://www.techwithtim.net/tutorials/machine-learning-python)
- ### RESOURCES
  - [GIT: ai-megaCourse](https://github.com/heidless-stillwater/ai-megaCourse)
  - [DATASETS: UC Irvine Machine Learning Repository](https://archive.ics.uci.edu/)
    - [Student Performance
](https://archive.ics.uci.edu/dataset/320/student+performance)
    - [Car Evaluation Dataset](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbmdXUTdHWl90X1gtS09UVk16OXZCazdIaU1jd3xBQ3Jtc0tsZUQxeFBaR0pqRDdMNzMwWHBnOHdSay1rT2lkUE56SnYxbXE0eTdVYVVnOWE1NG50OGpIcmJZdzNZRkFiTGlsbzVCOTNOOUZSUEhkWW9vTk1HN2U4ZUZ0VloyOGJKM1V6bUdmbDRTQU5QVlZOaWV2TQ&q=https%3A%2F%2Fdev-cms.us-east-1.linodeobjects.com%2FCar_Data_Set_1bd53a190c.zip&v=WFr2WgN9_xE)
  

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


## [02-nearest-neighbor](https://www.techwithtim.net/tutorials/machine-learning-python/k-nearest-neighbors-1)
### [KNeighborsClassifier](https://scikit-learn.org/dev/modules/generated/sklearn.neighbors.KNeighborsClassifier.html)
### k-nearest neighbor
Classification algorithm

$$

k:\ (HyperParameter)\ the\ amount\ of\ neighbors\ we're\ going\ to\ look\ for \\

m: distance

$$

$$
Euclidean\ Distance \\

m = d = \sqrt{(X_2-X_1)^2 + (y_2 - y_1)^2}\\


$$


## [Support Vector Machines (SVM)](https://www.techwithtim.net/tutorials/machine-learning-python/svm-1)
SVM stands for a support vector machine. SVM's are typically used for classification tasks similar to what we did with K Nearest Neighbors. They work very well for high dimensional data and are allow for us to classify data that does not have a linear correspondence.
