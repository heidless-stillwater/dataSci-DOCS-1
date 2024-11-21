# account & docs
ACCOUNT: heidlessemail09@gmail.com

Google Group Name: 'm-fv'

# [How to Deploy a Machine Learning Model to Google Cloud](https://www.youtube.com/watch?v=fw6NMQrYc6w&list=PLwHsEiLdJVW0WX5SLoPTq2HSwKCKeo0KW&index=1&t=493s)

# [cs329s-ml-deployment-tutorial](https://github.com/mrdbourke/cs329s-ml-deployment-tutorial)

```
git clone git@github.com:mrdbourke/cs329s-ml-deployment-tutorial.git

```

###################################
# conda with requirements.txt
#
conda config --add channels conda-forge

conda remove --all ml-fv 

conda deactivate
conda create --name ml-fv-10 pip python=3.8
conda activate ml-fv-10

conda install requests=2.25.1
conda install tensorflow=2.4.1
conda install streamlit=1.3.1
conda install google_api_python_client=1.12.8
conda install protobuf=3.14.0
conda install jupyter
conda install icecream


########
conda install jupyter
conda install numpy=1.23.5
conda install tensorflow=2.11.0
conda install streamlit


##########################
# google cloud credentials
# 
```
vi app.py
--

# Setup environment credentials (you'll need to change these)
os.environ["GOOGLE_APPLICATION_CREDENTIALS"] = "<GCP_KEY>" # change for your GCP key
PROJECT = "heidless-datasci" # change for your GCP project
REGION = "europe-west2" # change for your GCP region (where your model is hosted)

BUCKET = 'ml_deployment_bucket_0'
--

```


#########
# run app
#
streamlit run app.py

