# account & docs
ACCOUNT: heidlessemail09@gmail.com

Google Group Name: 'm-fv'


###################################
# conda with requirements.txt
#
conda config --add channels conda-forge

conda remove --all ml-fv 

conda deactivate
conda create --name ml-fv-3 pip python=3.8
conda activate ml-fv-5

conda install python=3.8
conda install jupyter
conda install protobuf=3.14.0
conda install requests=2.25.1
conda install tensorflow=2.4.1
conda install streamlit=0.76.0

conda install python=3.8 --channel conda-forge
conda install jupyter --channel conda-forge
conda install protobuf=3.14.0 --channel conda-forge
conda install requests=2.25.1  --channel conda-forge
conda install tensorflow=2.12 --channel conda-forge
conda install streamlit=0.76.0 --channel conda-forge
conda install icecream --channel conda-forge


###################

conda create --name food-vision-3 pip python=3.8
conda activate dataSci-2
conda activate food-vision-3


dataSci-2
- pip python 3.8


##################
## google.colab fix
## https://stackoverflow.com/questions/75666380/attributeerror-module-ipython-utils-traitlets-has-no-attribute-unicode
##################


conda install -c conda-forge google-colab

pip install google_api_python_client==1.12.8


#conda install request
#conda uninstall protobuf=3.14.0

#conda install tensorflow



## [How to Deploy a Machine Learning Model to Google Cloud](https://www.youtube.com/watch?v=fw6NMQrYc6w&list=PLwHsEiLdJVW0WX5SLoPTq2HSwKCKeo0KW&index=1&t=493s)

## [git: cs329s-ml-deployment-tutorial](https://github.com/mrdbourke/cs329s-ml-deployment-tutorial)

```
git clone git@github.com:mrdbourke/cs329s-ml-deployment-tutorial.git

```
### data source
- ### [Food-101 Overview](https://www.kaggle.com/code/kmader/food-101-overviews)


### google cloud credentials
```
vi app.py
--

# Setup environment credentials (you'll need to change these)
os.environ["GOOGLE_APPLICATION_CREDENTIALS"] = "heidless-datasci-53f93322658d.json" # change for your GCP key
PROJECT = "heidless-datasci" # change for your GCP project
REGION = "europe-west2" # change for your GCP region (where your model is hosted)

BUCKET = 'ml_deployment_bucket_0'
--

```

# run app
```
streamlit run app.py

```
