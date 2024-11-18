
# [How To Deploy ML Models With Google Cloud Run](https://www.youtube.com/watch?v=vieoHqt7pxo&list=PLwHsEiLdJVW0WX5SLoPTq2HSwKCKeo0KW&index=1)

## [ml-deployment](https://github.com/patrickloeber/ml-deployment)
#

# set env
```
source ~/miniconda3/bin/activate dataSci-2

jupyter lab

```

```

######################
# google-cloud-run app

conda install python=3.9

# requires python=3.9
conda install tensorflow

# build/run model
python train.py

python load.py

python test.py

```

## write app (flask, tensorflow)
[How To Deploy ML Models With Google Cloud Run](https://www.youtube.com/watch?v=vieoHqt7pxo&list=PLwHsEiLdJVW0WX5SLoPTq2HSwKCKeo0KW&index=2)

## setup gCloud
```
gcloud init
--
PROJECT:
heidless-datasci


## Cloud Build & deploy
gcloud builds submit --tag gcr.io/heidless-datasci/index

gcloud run deploy get-estimate \
     --platform managed \
     --region europe-west2 \
     --image gcr.io/heidless-datasci/index \
     --allow-unauthenticated

# gcloud run deploy --image gcr.io/heidless-datasci/index



# [TensorFlow 2 quickstart for beginners](https://www.tensorflow.org/tutorials/quickstart/beginner) 

```

# docker

docker build . -t get-estimate


