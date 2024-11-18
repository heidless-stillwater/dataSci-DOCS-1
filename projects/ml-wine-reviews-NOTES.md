
# account & docs
ACCOUNT: heidlessemail09@gmail.com

Google Group Name: 'ml-w'


# conda
```
conda deactivate
conda remove -n idd_back --all

conda create --name ml_db pip python=3.11
source ~/miniconda3/bin/activate ml_db

conda config --show channels
conda config --add channels conda-forge

conda env list

conda install jupyterlab --channel conda-forge
conda install jupyterthemes --channelc conda-forge

conda install torchvision --channel conda-forge

conda install numpy=1.26.4 --channel conda-forge
conda install pandas=2.2.2 --channel conda-forge
conda install matplotlib=3.8.0 --channel conda-forge
conda install scikit-learn=1.5.2 --channel conda-forge
conda install imbalanced-learn=0.12.4 --channel conda-forge
conda install tensorflow=2.15 --channel conda-forge
conda install tensorflow-hub=0.16.1 --channel conda-forge

conda install flask=3.0.3 --channel conda-forge
conda install pillow=11.0.0 --channel conda-forge

conda install pyyaml --channel conda-forge
conda install h5py --channel conda-forge

```

# [Python TensorFlow for Machine Learning – Neural Network Text Classification Tutorial](https://www.youtube.com/watch?v=VtRLrQ3Ev-U)

# [Google Colab](https://colab.research.google.com/)
```
NewNotebook->"kaggle-classification"

```

# Machine Learning Class Course
## What is machine learning
Machine learning is a subdomain of Computer Science that focuses on Algorithms which help a computer learn from data without explicit programming.

## AI vs ML vs DS
**Artificial Intelligence** is an ares of Computer Science where the goal is to enable machines to perform human-like tasks and simulate human behaviour.

**Machine Learning** is a subset of AI which tries to solve a specific problem and make prediction using data

**Data Science** is a field that attempts to find patterns and draw insights from data (might us ML)

All fields overlap. All may use ML?

## Types of Machine Learning
- **Supervised Learning** uses labeled inputs (meaning the input has a corresponding output label) to train models and learn outputs.
- **Un-Supervised Learning** uses unlabeled data to learn about patterns in the data
- **Reinforcement Learning** agent learning in interactive environment based on rewards and penalties 

## features
- **qualitative data** - categorical data (finite number of categories and groups)
  - NOMINAL data (no inherent order)
    - ONE-HOT Encoding
      - turns 'groups' into a vector
      - switches on with a '1' if category applies amd '0' if not.
  - ORDINAL data (NO inherent order)
- **quantitative** - numerical valued data (could be discrete or continuous)

## types of predictions
- **classification**
  - MULT-CLASS classification
  - BINARY-CLASS classification
- **regression** 
  - predict continuous values

# the MODEL
- ## how do we make the model learn
- ## how can we tell whether or not it's learning

## supervised learning dataset
- ## Training Dataset
- ## Validation Dataset
  - validation set used as a reality check during/after training to ensure the model can handle unseen data
- ## Testing Datase
  - Test set is used to ceck how generalizeable the final chosen model is

## metrics of performance
### L1 Loss
$$
loss = sum(|y_{real} - y_{predicted}|)
$$

### L2 Loss (Mean Squared Error)
$$
loss = sum((y_{real} - y_{predicted})^2)
$$

### accuracy

## loss functions
### Binary Closs-Entropy Loss
The losss decreases as the performance improves

$$
loss = 1-N*sum(y_{real}*log(y_{predicted})+(1-y_{real})*log((1-y_{predicted})))
$$

---

# Feedfsorward Neural Nets

## activation function
- SIGMOID
- TANH
- RELU

**ESSENTIAL**: Without the lon-leanear activation function this becomes a linear mobel 


## backpropogation
**GOAL** - decrease the LOSS

$$
w_{0.new} = w_{0.old} + \alpha^* \\
\alpha = learning\ rate

$$


## other Machine Learning Models
- ### Random Forest
- ### Linear regression
- ### Support Vector Machine

# machine learning

tensorflow - helps to develop & maintain ML model

# migrate worksheet to local env
```
ml-diabetes.ipynb

```

# Recurrent Neural Networks (RNN)

Utilizes back propogation thru time to ajust weights
## problems with RNN
- the RNN may end up being a deep network
- during backpropogation, we might be seeing the same terms over and over, due to the recuurent nature of the RNN.
  - exploding gradients
  - vanishing gradients

## GRUs and LSTMs
- ### Gated Recurrent Unit (GRU)
- ### Long Short-term Memory (LSTM)

---


