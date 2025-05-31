
#######################################################
# DEPLOY to LIVE
#
## submit to artifact registry
```
export GCP_PROJECT=h-pfolio-4
echo ${GCP_PROJECT}

#export APP_NAME=galaxy-poster
export APP_NAME=population-dashboard
#export APP_NAME=pretty-map
echo ${APP_NAME}

export GCP_REGION=europe-west2
echo ${GCP_REGION}

```

# build the APP environment
```
python -m venv venv
source ./venv/bin/activate

pip install -r streamlit-prettymapp/requirements.txt
pip install -r requirements.txt

#######
# LOCAL
```
streamlit run app.py

```

#####
# GCP
```
gcloud builds submit --tag gcr.io/${GCP_PROJECT}/${APP_NAME}  --project=${GCP_PROJECT}

gcloud run deploy --image gcr.io/${GCP_PROJECT}/${APP_NAME} --platform managed  --project=${GCP_PROJECT} --allow-unauthenticated

```


############################

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
docker build -t dash-0 .

# Run the image
docker run -p 8080:8080 dash-0



streamlit run test_estimate.py
