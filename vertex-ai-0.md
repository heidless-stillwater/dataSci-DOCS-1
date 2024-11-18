
# [Vertex AI Tutorial: A Comprehensive Guide For Beginners](https://www.datacamp.com/tutorial/vertex-ai-tutorial)


# set env
```
source ~/miniconda3/bin/activate dataSci-2

jupyter lab

```


## dataset
### [dry bean dataset](https://archive.ics.uci.edu/dataset/602/dry+bean+dataset)


## convert xlsx to csv
```
jupyter lab 
--
convert-to-csv.ipynb
--

```

#########
## gCloud
```
gcloud init

```

## google BUCKET
```
export GCP_PROJECT=vertex-0
export GCP_BUCKET=dry_bean_0
export GCP_REGION=europe-west2

echo ' '
echo GCP_PROJECT: ${GCP_PROJECT}

echo GCP_BUCKET: ${GCP_BUCKET}
echo GCP_REGION: ${GCP_REGION}
export bucket_path='gs://'${GCP_BUCKET}
echo $bucket_path
gsutil mb -l ${GCP_REGION} ${bucket_path}

## [bucket permissions]()
gsutil iam ch allUsers:objectViewer $bucket_path

```


# vertex ai
### Ingest a local CSV into Vertex AI
```
Datasets->Create
--
Name:
dry_bean_data_0

--

Tabular->RegressionOrClassificvation

CREATE

<Upload CSV files from your computer>

```

## configure workbench
```
NOTEBOOKS->Worbench->CreateNew-AdvencedOptions:
--
Name:
ml-0-worbench

Region:
europe-west2

MachineType:
n1-standard-1

Idls Shutdown:
10

<CREATE>

<OPEN JUPYTERLAB>

--

```

notebook_template.ipynb
```
<step through setup>

```

# Training and Deploying AutoML Models in Vertex AI

## Loading data from a Google Storage bucket
```

import pandas as pd

# Path to your CSV file in GCS bucket
gcs_path = "gs://dry_bean_0-vertex-0-unique/dry_bean.csv"

beans = pd.read_csv(gcs_path)

beans.head()

```

# Deploying an AutoML model and generating predictions
```
endpoint = model.deploy(machine_type="n1-standard-4")

```

# export & download
gsutil cp -r gs://dry_bean_0 ./download_dir


