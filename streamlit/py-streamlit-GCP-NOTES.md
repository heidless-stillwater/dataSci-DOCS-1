
## [Building Your First Streamlit App: A Step-by-Step Tutorial](https://medium.com/@chaitanyasirivuri/building-your-first-streamlit-app-a-step-by-step-tutorial-e058d5dfe5f4)

conda deactivate
source ~/miniconda3/bin/activate ml_datasci


## RUN
```
streamlit run app.py


```

## Google DEPLOY

### [How to deploy your Streamlit Web App to Google Cloud Run](https://medium.com/@faizififita1/how-to-deploy-your-streamlit-web-app-to-google-cloud-run-ba776487c5fe)

### Generate requirements.txt
```
conda list -e > requirements.txt

```

```
# Dockerfile
FROM python:3.11
EXPOSE 8080
WORKDIR /app
COPY . ./
RUN pip install -r requirements.txt
ENTRYPOINT ["streamlit", "run", "app.py", "--server.port=8080", "--server.address=0.0.0.0"]

```

# configure Docker
- ### [How to Conda (miniconda / anaconda) in Docker in 2022](https://mjtdev.medium.com/how-to-conda-miniconda-anaconda-in-docker-in-2022-5579cafc44fd)
  - ### [Export and Create conda environment with yml](https://shandou.medium.com/export-and-create-conda-environment-with-yml-5de619fe5a2)
```
conda env export > environment.yml

conda env create -f environment.yml

```
- ### [Activating a Conda environment in your Dockerfile](https://pythonspeed.com/articles/activate-conda-dockerfile/#working)
  - ### [Docker for Development and Deployment](https://mjtdev.medium.com/how-to-conda-miniconda-anaconda-in-docker-in-2022-5579cafc44fd)

```
     # Dockerfile
     
     conda install conda-forge::docker

     conda list -e > requirements.txt
     conda create --name ml_datasci --file requirements.txt

     ```


# build & run container
```
# Build a local docker image
docker build -t s_app .

# Run the image
docker run -p 8080:8080 s_app

```

# google submit & deploy

export GCP_PROJECT=heidless-datasci
echo ${GCP_PROJECT}

export APP_NAME=id-digit-frontend
echo ${APP_NAME}

export GCP_SERVICE_NAME=${APP_NAME}-svc
echo ${GCP_SERVICE_NAME}

export GCP_REGION=europe-west2
echo ${GCP_REGION}

gcloud builds submit --tag gcr.io/${GCP_PROJECT}/${GCP_SERVICE_NAME} --timeout=2h

gcloud run deploy ${GCP_SERVICE_NAME} \
     --platform managed \
     --region ${GCP_REGION} \
     --image gcr.io/${GCP_PROJECT}/${GCP_SERVICE_NAME} \
     --allow-unauthenticated
