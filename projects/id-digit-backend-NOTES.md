
# account & docs
ACCOUNT: heidlessemail09@gmail.com

Google Group Name: 'ml-d'


# [google: cost mgmt](https://console.cloud.google.com/billing/01FE37-94F24B-C379DD/reports/cost-breakdown?hl=en)
# [tensorflow beginner course](https://www.youtube.com/watch?v=hvgnX1gbsLA&list=PLqnslRFeH2Uqfv1Vz3DqeQfy0w20ldbaV&index=1)

# [How To Deploy ML Models With Google Cloud Run](https://www.youtube.com/watch?v=vieoHqt7pxo&t=75s)
- ## [ml-deployment](https://github.com/patrickloeber/ml-deployment/tree/main)

conda remove -n <ENV_NAME> --all

conda remove -n food-vision-3 --all

conda config --show channels
conda config --add channels conda-forge

conda env list

#conda create --name cloud_run_3 pip python=3.9

source ~/miniconda3/bin/activate idd_back
conda deactivate

<!-- 
conda install Flask --channel conda-forge
conda install gunicorn --channel conda-forge
conda install tensorflow=2.15 --channel conda-forge
conda install numpy --channel conda-forge
conda install pillow --channel conda-forge

conda install jupyter
conda install streamlit=1.3.1 --channel conda-forge
conda install requests=2.25.1 --channel conda-forge
conda install protobuf=3.14.0 --channel conda-forge

google_api_python_client==1.12.8
 -->

conda uninstall python=3.9
conda install python=3.8

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


## NOTES
```
ValueError: Argument(s) not recognized: {'lr': 0.001}
--
# change 'lr' to 'learning_rate'
optim = keras.optimizers.Adam(learning_rates=0.001)

--

```



# OPERATION
- ## run server
  ```
  cd <home>
  python main.py

  ```

- ## test predictions
  ```
  cd test
  python test.py

  ```

# Google DEPLOY

export GCP_PROJECT=heidless-datasci

```
gcloud init

gcloud builds submit --tag gcr.io/heidless-datasci/index

gcloud run deploy --image gcr.io/heidless-datasci/index --platform managed
--
NAME:
id-digit-backend-svc

RE19GION:
europe-west2

--

```
