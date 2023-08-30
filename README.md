# Django Python Docker Web App Deployment

This repository contains the code and instructions to deploy a Django Python web app using Docker on an AWS EC2 instance.

## Prerequisites

Before you begin, ensure you have the following:

- An AWS EC2 instance with Docker installed.
- Make sure your EC2 security group allows inbound traffic on port 8000. (Add a custom tcp rule allowing anywhere traffic on port 8000)
- A GitHub repository with your Django Python web app code.

##Commands and Steps:

-Update and upgrade packages:

```
    sudo apt-get update -y && sudo apt-get upgrade -y
```
-Install Docker:

```
    sudo apt install docker.io -y
```
-Add your user to the docker group to avoid using sudo with Docker commands:

```
    sudo usermod -aG docker ubuntu
```
-Clone your GitHub repository containing the Django Python web app code:

```
    git clone https://github.com/your-username/your-repo.git
```
-Build your Docker image using the Dockerfile in your repository:

```
    docker build -t ghostiexd/django-python-webapp:latest .
```
-Check if the image was created:

```
    docker images
```
-Run the Docker container, mapping port 8000:

```
    docker run -it -p 8000:8000 ghostiexd/django-python-webapp:latest
```
-Your Django web app should now be accessible at

```
    http://<ec2-public-ip>:8000/demo/
```
-Log in to Docker Hub:

```
    docker login
```
-Push your Docker image to Docker Hub:

```
    docker push ghostiexd/django-python-webapp:latest
```
## Notes

-Customize and modify the Dockerfile to suit your application's requirements.
