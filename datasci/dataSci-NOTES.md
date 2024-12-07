- [environment](#environment)
	- [Cookiecutter](#cookiecutter)
	- [set env](#set-env)
	- [markdown cheatsheet](#markdown-cheatsheet)
	- [git cheatsheet](#git-cheatsheet)
	- [conda](#conda)
		- [conda - CHEATSHEET](#conda---cheatsheet)
	- [jupyter notebooks](#jupyter-notebooks)
- [ml-project-A](#ml-project-a)
	- [API: google-cloud-run](#api-google-cloud-run)
	- [GUI: streamlit-deploy](#gui-streamlit-deploy)
- [population-dashboard](#population-dashboard)
	- [population-dashboard-NOTES.md](#population-dashboard-notesmd)
	- [git: population dashboard](#git-population-dashboard)
- [Build Your First Machine Learning Project \[Full Beginner Walkthrough\]](#build-your-first-machine-learning-project-full-beginner-walkthrough)
	- [git: project\_walkthroughs: beginner\_ml](#git-project_walkthroughs-beginner_ml)
		- [gCloud Vertex AI](#gcloud-vertex-ai)
		- [install packages](#install-packages)


# environment
## [Cookiecutter](https://www.cookiecutter.io/)
- ### [Data Science](https://github.com/drivendataorg/cookiecutter-data-science)
  - [7 Tips To Structure Your Python Data Science Projects](https://www.youtube.com/watch?v=xVuqDBCQAYc)
- ### [Django](https://github.com/cookiecutter/cookiecutter-django)
- ### python
  - ### [python-package-template](https://github.com/TezRomacH/python-package-template)
  - 
## set env
```
source ~/miniconda3/bin/activate dataSci-2

jupyter lab

```
## markdown cheatsheet
- ### [markdown](https://github.com/adam-p/markdown-here/wiki/markdown-cheatsheet)


## git cheatsheet
```
git clone git@github.com:heidless-stillwater/population-dashboard.git

# rename 'master' to 'main'
# LOCAL
git branch -m master main
git status

# REMOTE - Settings->DefaultBranch
git push -u origin main
git push origin --delete master

```

## conda
```

# install
mkdir -p ~/miniconda3
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
zsh ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm ~/miniconda3/miniconda.sh

# initialize on all available shellls
s
conda init --all

# activate
source ~/miniconda3/bin/activate dataSci-0

```

### [conda - CHEATSHEET](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf)
```
############
# manage ENV
#
conda remove -n <ENV_NAME> --all

conda remove -n idd_back --all

conda config --show channels
conda config --add channels conda-forge

conda env list

conda create --name dataSci-0 
source activate dataSci-0

conda create --name dataSci-2 python=3.13
source ~/miniconda3/bin/activate dataSci-2

conda create --name cloud_run_0 pip python=3.11
source ~/miniconda3/bin/activate cloud_run_0

conda env list		# show all environments

conda list		# show installed packages

#########################
# install/remove packages
#
#conda uninstall python=3.9
#conda install python=3.8

conda install scipy --channel conda-forge

#######################
# environment.yml mgmnt
#
conda env export > pop_dash.yml

conda deactivate

# id-digit-backend
conda env create --name pop_dash --file=idd_back_env.yml
source ~/miniconda3/bin/activate pop_dash



```

## jupyter notebooks
```
source ~/miniconda3/bin/activate dataSci-2

conda install jupyterlab --channel conda-forge

conda install -c conda-forge jupyterthemes
--
jt -l

jt -t <theme-name>

--


jupyter lab

```

# ml-project-A
## API: google-cloud-run
## GUI: streamlit-deploy

# population-dashboard
## population-dashboard-NOTES.md
## [git: population dashboard](git@github.com:heidless-stillwater/population-dashboard.git)

---
# [Build Your First Machine Learning Project [Full Beginner Walkthrough]](https://www.youtube.com/watch?v=Hr06nSA-qww&list=PLwHsEiLdJVW0WX5SLoPTq2HSwKCKeo0KW&index=2&t=10s)

## [git: project_walkthroughs: beginner_ml](https://github.com/dataquestio/project-walkthroughs/tree/master/beginner_ml)


### [gCloud Vertex AI](https://cloud.google.com/vertex-ai/docs/tutorials/jupyter-notebooks)


### install packages
```
conda install pandas --channel conda-forge
conda install numpy --channel conda-forge
conda install seaborn --channel conda-forge
conda install scikit-learn --channel conda-forge
conda install openpyxl --channel conda-forge
conda install tensorflow --channel conda-forge
conda install flask --channel conda-forge
conda install streamlit --channel conda-forge

conda install -c conda-forge google-colab


############
# tensorflow

# only works with python <= Version 3.11
conda install python=3.9
python -V

#conda install tensorflow=2.15
conda install tensorflow=2.17
#conda install tensorflow=2.13

#pip install tf-models-official

# test installation
python -c "import tensorflow as tf; x = [[2.]]; print('tensorflow version', tf.__version__);print('hello, {}'.format(tf.matmul(x, x)))"

# Verify the installation:
python3 -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"

vi test.py
--
import tensorflow as tf

hello = tf.constant("Hello World!")

with tf.compat.v1.Session() as sess:
  result = sess.run(hello)
  print(resukt.decode())

--

```
