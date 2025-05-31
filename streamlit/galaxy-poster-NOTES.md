
#######################################################
# DEPLOY to LIVE
#
## submit to artifact registry
```
export GCP_PROJECT=h-pfolio-4
echo ${GCP_PROJECT}

export APP_NAME=galaxy-poster-2
echo ${APP_NAME}

export GCP_REGION=europe-west2
echo ${GCP_REGION}

gcloud builds submit \
  --tag gcr.io/${GCP_PROJECT}/${APP_NAME} \
  --project=${GCP_PROJECT} \
  --timeout=2h

```
## deploy to live
```
gcloud run deploy ${APP_NAME} \
  --image gcr.io/${GCP_PROJECT}/${APP_NAME} \
  --region ${GCP_REGION} \
  --platform managed  \
  --project=${GCP_PROJECT} \
  --allow-unauthenticated

```

##############################################################
# misc

# build svc via google dashboard
CloudRun->DeployContainer->Service->[container image url]
--
Allow Unauthenticated Invocations
--

```




###########################################
# population dashboard as example
## [Building a dashboard in Python using Streamlit](https://blog.streamlit.io/crafting-a-dashboard-app-in-python-using-streamlit/)
- ### [git: population-dashboard](git@github.com:heidless-stillwater/population-dashboard.git)

## git
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
# init DOCKERFILE
```
# Use the official lightweight Python image.
# https://hub.docker.com/_/python
FROM python:3

# Allow statements and log messages to immediately appear in the Knative logs
ENV PYTHONUNBUFFERED True

EXPOSE 8080

# Copy local code to the container image.
ENV APP_HOME /app
WORKDIR $APP_HOME
COPY . ./

# Install production dependencies.
RUN pip install -r requirements.txt

# Run the web service on container startup. Here we use the gunicorn
# webserver, with one worker process and 8 threads.
# For environments with multiple CPU cores, increase the number of workers
# to be equal to the cores available.
# Timeout is set to 0 to disable the timeouts of the workers to allow Cloud Run to handle instance scaling.
CMD streamlit run --server.port 8080 --server.enableCORS false streamlit_app.py

```

# build the APP environment
```
python -m venv venv
source ./venv/bin/activate

pip install -r requirements.txt

# RUN
```
streamlit run app.py

```

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
