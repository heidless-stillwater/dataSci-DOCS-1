
# [Building Your First Streamlit App: A Step-by-Step Tutorial](https://medium.com/@chaitanyasirivuri/building-your-first-streamlit-app-a-step-by-step-tutorial-e058d5dfe5f4)

conda remove -n <ENV_NAME> --all

conda remove -n idd_back --all

conda config --show channels
conda config --add channels conda-forge

conda env list

conda create --name streamlit_3 pip python=3.11

conda deactivate
source ~/miniconda3/bin/activate idd_front

conda install jupyter --channel conda-forge
conda install streamlit --channel conda-forge


# RUN
```
streamlit run app.py


```

# Google DEPLOY

## [How to deploy your Streamlit Web App to Google Cloud Run](https://medium.com/@faizififita1/how-to-deploy-your-streamlit-web-app-to-google-cloud-run-ba776487c5fe)

```
# Dockerfile
FROM python:3.11
EXPOSE 8080
WORKDIR /app
COPY . ./
RUN pip install -r requirements.txt
ENTRYPOINT ["streamlit", "run", "app.py", "--server.port=8080", "--server.address=0.0.0.0"]

```

# build & run container
```
# Build a local docker image
docker build -t id-digit-frontend .

# Run the image
docker run -p 8080:8080 id-digit-frontend

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
