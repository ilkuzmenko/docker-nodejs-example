# Docker Task
Dockerize node.js app, write my own Dockerfile. Run container with CPU and RAM restrictions. Node.js app must be on 80 port. Create Docker Hub account. Add my docker image to my public repository. Write used CLI commands to README.md.

## Build and run
Build Dockerfile <br/>
`docker build -t app:devops-lab .`

Run docker-image with name, add restrictions on use CPU and RAM <br/>
`docker run --name devops-lab -p 80:80 --cpus=1 --memory=512m app:devops-lab`

Check docker stats <br/>
`docker stats`

## Docker Hub usage

Log in to Docker Hub <br/>
`docker login`

Add docker tag for push image to Docker Hub <br/>
`docker tag <docker-image-ID> illiakuzmenko/devops-lab:v1.0`

Push image to Docker Hub <br/>
`docker push myusername/myimage:v1.0`

Pull the Docker image <br/>
`docker pull illiakuzmenko/devops-lab:v1.0`

Run a Docker container using the pulled image <br/>
`docker run --name devops-lab -p 80:80 --cpus=1 --memory=512m illiakuzmenko/devops-lab:v1.0`

Verify the container <br/>
`docker ps`

Update image version on Docker Hub <br/>
`docker build -t illiakuzmenko/devops-lab:v2.0 .`

Push updated image to the Hub <br/>
`docker push illiakuzmenko/devops-lab:v2.0 .`

List the Docker images that you have pulled from Docker Hub <br/>
`docker images`

# Kubernetes Task
Create a Deployment from the docker container. The pod should have nginx before nodejs (work as a reverse proxy). Be sure to do a liveness probe (httpget). Run 3 copies of the application.

## Commands kubectl

To apply the Deployment configuration<br/>
`kubectl apply -f deployment.yaml`

To get one of the running pods <br/>
`kubectl get pods -l app=app-name`

To delete Deployment from your Kubernetes cluster<br/>
`kubectl delete deploy app-deployment`
