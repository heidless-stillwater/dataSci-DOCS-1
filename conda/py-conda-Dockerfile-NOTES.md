
# [Step-By-Step: Creating a Docker Image for Your Data Science Project](https://haveagreatdata.com/posts/step-by-step-docker-image-for-data-science-projects/)

```
docker build -t s_app:latest .
docker build -t i_digit:latest .

docker run -it s_app
docker run -it i_digit

docker logs --since=1h magical_edison

```
