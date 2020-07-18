# docker-repo
I create docker images for different purposes and use this place to store them

# Installing Docker

Installing with convenience script:

`$ curl -fsSL https://get.docker.com -o get-docker.sh`

`$ sudo sh get-docker.sh`

To run docker as a non-root user

`$ sudo usermod -aG docker your-user`

## Pushing Images to the repository

1. Login to the docker hub with `$ docker login --username=<your-username> --email=<email@domain.com>`

2. Now tag the image present locally with the repository name, like this: `$ docker tag <image-hash` <your-username>/<repo-name>:<tag>`

3. After that, the image is ready to be pushed. Do it with the following command: `$ docker push <your-username>/<repo-name>`

# Removing all containers

`sudo docker rm $(sudo docker container ls -aq)`

[Reference](https://docs.docker.com/engine/install/ubuntu/)
