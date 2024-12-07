
# [Building a dashboard in Python using Streamlit](https://blog.streamlit.io/crafting-a-dashboard-app-in-python-using-streamlit/)
- # [git: population-dashboard](git@github.com:heidless-stillwater/population-dashboard.git)

# git
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

# build the APP environment
conda create --name pop_dash pip python=3.11
source ~/miniconda3/bin/activate pop_dash

conda install jupyter --channel conda-forge
conda install streamlit --channel conda-forge
conda install pandas --channel conda-forge
conda install altair --channel conda-forge
conda install plotly --channel conda-forge
conda install vega_datasets --channel conda-forge
conda install kagglehub --channel conda-forge

#conda uninstall python=3.9
#conda install python=3.8



# RUN
```
streamlit run streamlit_app.py


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
docker build -t dash-0 .

# Run the image
docker run -p 8080:8080 dash-0

```

# google submit & deploy

export GCP_PROJECT=heidless-datasci
echo ${GCP_PROJECT}

export APP_NAME=streamlit-dash-0
echo ${APP_NAME}

gcloud builds submit --tag gcr.io/${GCP_PROJECT}/${APP_NAME} --timeout=2h

# build svc via google dashboard


streamlit run test_estimate.py
