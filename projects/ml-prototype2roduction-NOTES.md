# account & docs
ACCOUNT: heidlessemail09@gmail.com

Google Group Name: 'ml-p2p'

# conda
```
conda config --show channels

conda deactivate

conda remove --all -n cloud_run_0 

export ML_ENV=ml_p2p
conda create --name ${ML_ENV} pip python=3.11
source ~/miniconda3/bin/activate ml_p2p

conda config --add channels conda-forge

conda env list
conda install jupyterlab --channel conda-forge

conda install os --channel conda-forge

conda install tensorflow=2.15 --channel conda-forge
conda install tensorflow-hub=0.16.1 --channel conda-forge
conda install icecream --channel conda-forge

pip install icecream

conda env create -f environment.yml

[Export and Create conda environment with yml](https://shandou.medium.com/export-and-create-conda-environment-with-yml-5de619fe5a2)
--

# create environment.yml file
conda env export > environment_droplet.yml

# create conda environment from environment.yml
conda env create -f environment.yml

# list all the conda environment available
conda info --envs 

# Create new environment named as `envname`
conda create --name envname

# Remove environment and its dependencies
conda remove --name envname --all

# Clone an existing environment
conda create --name clone_envname --clone envname

--


#conda install torchvision --channel conda-forge

#conda install numpy=1.26.4 --channel conda-forge
#conda install pandas=2.2.2 --channel conda-forge
#conda install matplotlib=3.8.0 --channel conda-forge
##conda install scikit-learn=1.5.2 --channel conda-forge
#conda install imbalanced-learn=0.12.4 --channel conda-forge

#conda install flask=3.0.3 --channel conda-forge
#conda install pillow=11.0.0 --channel conda-forge

#conda install pyyaml --channel conda-forge
#conda install h5py --channel conda-forge

```

####################### 
# Vertex AI Env - RESEARCH
- ## [Vertex AI: Workbench & Env setup](https://www.cloudskillsboost.google/paths/371/course_templates/1123/video/495131)
- ## [Add a conda environment](https://cloud.google.com/vertex-ai/docs/workbench/instances/add-environment)
  ```
  conda create -n ml_p2p
  conda activate myenv
  conda install pip
  conda config --add channels conda-forge

  pip install -r requirements.txt
  
  DL_ANACONDA_ENV_HOME="${DL_ANACONDA_HOME}/envs/myenv"
  
  python -m ipykernel install --prefix "${DL_ANACONDA_ENV_HOME}" --name myenv --display-name myenv

  ```

# [#prototype2production](https://www.youtube.com/hashtag/prototype2production)
## [Getting started with Notebooks for machine learning](https://www.youtube.com/watch?v=_Q1Nf-rgSiE)
- ### [Vertex AI](https://console.cloud.google.com/vertex-ai?referrer=search&hl=en&project=vertex-0)

```
Workbench->ManagedNotebooks->CreateNew
--

# Advanced Options

flowers-5
europe-west4

# environment
--
Python 3.10

--

# Machine Type
e2-standard-4

# IAM & Security
--
Service Account
Enable Terminal Access

--

# Machine Type
--
n1-standard--1
Shutdown after Inactivity: 20mins

--

CREATE

Open JupyterLab
- Kernel: Tensorflow 2.12

```

## build ENV
```
##################
# init environment
#
# default sudo password for 'jupyter' is 'jupyter'
#
#sudo apt-get python3
#sude apt-get -y install python3-pip
#python3 -m pip install --user --upgrade pip
#python3 -m venv env
#source env/bin/activate
--

```

## [Storing data for machine learning](https://www.youtube.com/watch?v=txj_YprD5zM)

- ### [colab notebook](https://colab.research.google.com/github/nikitamaia/tensorflow-examples/blob/main/task.ipynb)

```
jupyter lab -> task.ipynb

# get project id
gcloud config list --format 'value(core.project)'

--
## in Terminal
source env-vars

PROJECT_ID=${GCP_PROJECT_ID}
echo PROJECT_ID: ${PROJECT_ID}

BUCKET="gs://${GCP_BUCKET}"
echo BUCKET: ${BUCKET}
gsutil mb -l ${GCP_REGION} ${BUCKET}

# download and untar dataset
wget https://storage.googleapis.com/download.tensorflow.org/example_images/flower_photos.tgz
tar xvzf flower_photos.tgz

# copy dataset to bucket
gsutil -m cp -r flower_photos $BUCKET

#
# downloads to ~/.keras/datasets/flower_photos.tgz
#

dataset_url = "https://storage.googleapis.com/download.tensorflow.org/example_images/flower_photos.tgz"

data_dir = tf.keras.utils.get_file('flower_photos', origin=dataset_url, untar=True)

data_dir = pathlib.Path(data_dir)

--

```

## GCP Storage Bucket
- ## access google
  ```
  gcloud init

  source ./.env-vars

  ```

## [Training custom models on Vertex AI](https://www.youtube.com/watch?v=VRQXIiNLdAk)

## Running a custom training job
- ### export notebook to python file 
  ```
  # create 'py' version of 'ipynb' notebook
  jupyter nbconvert task.ipynb --to python

  jupyter nbconvert build-training-job.ipynb --to python
  
- ### update code to
  ```
  gs://proto2prod-bucket-0

  ```
  - #### read data from Cloud Storage
  - #### write data to Cloud Storage
  - 
- ### Containerize Code
```
gcloud init

IMAGE_URI=${GCP_REGION}-docker.pkg.dev/${GCP_PROJECT_ID}/${GCP_REPO_NAME}/flower_image:sslatest

IMAGE_URI=europe-west4-docker.pkg.dev/394099236728/ml-flower-repo/flower_image:latest
echo IMAGE_URI: ${IMAGE_URI}

#gcloud builds submit --tag "europe-west4-docker.pkg.dev/394099236728/ml-flower-repo/flower_image"

```

## [The following quota metrics exceed quota limits: aiplatform.googleapis.com/custom_model_training_cpus](https://console.cloud.google.com/iam-admin/quotas?inv=1&invt=AbhZ9g&project=h-data-science)

#######
# build
#
docker build ./ -t ${IMAGE_URI}

######
# push 
# image to Artifact registry
#
#docker push ${IMAGE_URI}

gcloud builds submit --tag gcr.io/h-data-science/flower-testbuild-0

# train new model
GoogleGui->vertexAI->training->TrainNewMpdel
--
Custom Training Advanced
Custom Container
->  gcr.io/heidless-datasci
    -> flower-train-build
Model Output Directory
Deploy to new worker pool
-> Worker Pool 0
n1-standard-4

--

gcloud run deploy --image gcr.io/heidless-datasci/index --platform managed
--
NAME:
id-digit-backend-svc

RE19GION:
europe-west2



```

- ### Launch Training job
- 

# Vertex API - Predictions

- ### import model
```
VertextAI-Models-Import
``
Name:
flower-predict

Prebuilt:
tensorflow 2.12

``

BrowseStorage-{BUCKET}->model-output

IMPORT

```

## Deploy to Endpoint'

ModelRegistry->{Newly CreatedModel}->DeployToEndPoint



