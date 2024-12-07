# account & docs
```
ACCOUNT: heidlessemail09@gmail.com

Google Group Name: 's_GCP'

```

# conda
```
source ~/miniconda3/bin/activate ml_datasci

conda deactivate

```

# streamlit account
- ### [heidless-stillwater's apps](https://share.streamlit.io/)


# tut
## [Deploy a Streamlit application on Google Cloud Run - all you need to know](https://www.youtube.com/watch?v=LxwoCKM1Qik&t=1s)

### [create an app](https://docs.streamlit.io/get-started/tutorials/create-an-app)
```
# env
python -m venv venv
source ./venv/bin/activate

```

# Build and deploy
Command to build the application. PLease remeber to change the project name and application name
```
# gcloud builds submit --tag gcr.io/<PROJECT>/galaxtpost  --project=<PROJECT>

gcloud builds submit --tag gcr.io/h-pfolio-1/galaxypost  --project=h-pfolio-1
gcloud builds submit --tag gcr.io/h-pfolio-1/popdash  --project=h-pfolio-1
gcloud builds submit --tag gcr.io/h-pfolio-1/prettymapp  --project=h-pfolio-1

```

# Command to deploy the application
```
# gcloud run deploy --image gcr.io/<PROJECT>/galaxtpost --platform managed  --project=<PROJECT> --allow-unauthenticated

gcloud run deploy --image gcr.io/h-pfolio-1/galaxypost --platform managed  --project=h-pfolio-1 --allow-unauthenticated
gcloud run deploy --image gcr.io/h-pfolio-1/popdash --platform managed  --project=h-pfolio-1 --allow-unauthenticated
gcloud run deploy --image gcr.io/h-pfolio-1/prettymapp --platform managed  --project=h-pfolio-1 --allow-unauthenticated

```

# move images
mv gz_icon.jpeg /mnt/c/Users/heaidless/Downloads/

