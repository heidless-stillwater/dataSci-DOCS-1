# markdown maths cheatsheet
### [Cheat Sheet: Adding Math Notation to Markdown](https://www.upyesp.org/posts/makrdown-vscode-math-notation/#:~:text=Including%20Math%20Notation%20in%20Markdown&text=Inline%20math%20notation%20is%20wrapped,signs%2C%20wrapped%20inside%20triple%20backticks.)

# account & doc
```
ACCOUNT: heidlessemail09@gmail.com

Google Group Name: 'ai_mc'

```

# env

### conda
conda create --name ai_neural pip python=3.11
source ~/miniconda3/bin/activate ai_neural

conda install tensorflow
conda install streamlit

conda install logging

conda install matplotlib
conda install pandas
conda install icecream

conda install plotly

### pip
#### Problem 'No Module Named ‘tensorflow’' When using 'streamlit'
#### solution
- python version 3.12 possibly the problem
- try setting to 3.19 - using pyenv
- 
### pyenv
#### [GIT: install pyenv from here](https://github.com/pyenv/pyenv?tab=readme-ov-file#1-automatic-installer-recommended)
```
# auto installer
curl https://pyenv.run | zsh

# update env
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo '[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init -)"' >> ~/.zshrc

# restart shell
exec "$SHELL"

# install python build dependencies
sudo apt update; sudo apt install build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev curl git \
libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev

# usage  
pyenv versions

```

#### [Managing Multiple Python Versions With pyenv](https://realpython.com/intro-to-pyenv/)
```
# list available versions
pyenv install --list | grep " 3\.[123456789]"
--
3.9.21    # set as default
3.12.8

--

# list installed
#pyenv install --list 
pyenv versions

pyenv install 3.9.21
pyenv install 3.11.11
pyenv install 3.12.8

# use VERSION
pyenv global 3.11.11


```

#### [FIX: No Module Named ‘tensorflow’](https://pyimagesearch.com/2024/07/29/no-module-named-tensorflow/)
```
# reset python version
python --version

# switch to python version
sudo update-alternatives --install /usr/bin/python python /usr/bin/python3 1


```



```
source venv/bin/activate

# install
pip install tensorflow

# # install nightly build - up to minute features - MEY BE UNSTABLE
# pip install tf-nightly

# verify installation
python
--
import tensorflow as tf
print(tf.__version__)

--


```
# generate requirements.txt
pip list --format=freeze > requirements.txt

# replace tensorflow with :
--
# For GPU users
pip install tensorflow[and-cuda]
# For CPU users
pip install tensorflow

--



pip install streamlit

#pip install numpy 
pip install pandas
pip install matplotlib

pip install plotly   

pip install loggingy

pip install icecream


# project

/home/heidless/projects/heidless-python/dataSci-APPS-2/sandbox/datasci/

/home/heidless/projects/heidless-python/dataSci-APPS-2/sandbox/datasci/

AIMegaCourse

[ai-megaCourse](https://github.com/heidless-stillwater/ai-megaCourse)

```

## [tech with tim: machine learning - neural networks](https://www.techwithtim.net/tutorials/machine-learning-python)
- ### Resources
  - [YouTube: Python Machine Learning & AI Mega Course - Learn 4 Different Areas of ML & AI](https://www.youtube.com/watch?v=WFr2WgN9_xE&t=217s)
  - [GIT: ai-megaCourse](https://github.com/heidless-stillwater/ai-megaCourse)
  - [DATASETS: UC Irvine Machine Learning Repository](https://archive.ics.uci.edu/)
    - [Student Performance
](https://archive.ics.uci.edu/dataset/320/student+performance)
    - [Car Evaluation Dataset](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbmdXUTdHWl90X1gtS09UVk16OXZCazdIaU1jd3xBQ3Jtc0tsZUQxeFBaR0pqRDdMNzMwWHBnOHdSay1rT2lkUE56SnYxbXE0eTdVYVVnOWE1NG50OGpIcmJZdzNZRkFiTGlsbzVCOTNOOUZSUEhkWW9vTk1HN2U4ZUZ0VloyOGJKM1V6bUdmbDRTQU5QVlZOaWV2TQ&q=https%3A%2F%2Fdev-cms.us-east-1.linodeobjects.com%2FCar_Data_Set_1bd53a190c.zip&v=WFr2WgN9_xE)
  - ### keras
    - fashion: keras.datasets.fashion_mnist


# intro
In a neural network, **weights** and **biases** are parameters that are learned during training and adjust the strength of connections between neurons and the output of neurons: 

#### Weights

Control the strength of the connection between neurons and determine how much influence input has on the output. 

Weights are real values that are adjusted during training to optimize the network's performance.

#### Biases

Constants that are added to neurons to ensure activation even when there is no input. 

Biases are positive or negative and can increase or decrease a neuron's output. 

Weights and biases are adjusted in the hidden layers of a neural network, which are the layers between the input and output layers. 
This process is called **forward and backward propagation**. 

$$
\sum_{i=1}^{i}(V_1 * W_1) + b
$$

### activation function

$$
f[\sum_{i=1}^{i}(V_1 * W_1) + b] = f(x) = activation\ function
$$

- #### sigmoid
  - maps input values to between -1 & 1

- #### rectify linear unit
    - all negative values = 0
    - all positive values = enhanced positivehttps://www.tensorflow.org/tutorials/keras/classification


### loss function
Calculates Error: tells your how 'wrong' your answer is

Determines how weights & biases are adjusted

# tensorflow
### resources
- #### [Example: Basic classification: Classify images of clothing](https://www.tensorflow.org/tutorials/keras/classification)

```


```