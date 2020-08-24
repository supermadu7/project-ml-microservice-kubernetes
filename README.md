[![CircleCI](https://circleci.com/gh/supermadu7/project-ml-microservice-kubernetes.svg?style=svg)](https://circleci.com/gh/supermadu7/project-ml-microservice-kubernetes)


## Project Overview

This project is about operationalizing a machine learning microservice API. The project uses kubernetes which is an open-source system for automating the management of containerized applications. In the project we implemented a pre-trained sklearn model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.


### Instructions on how to run the Python scripts and web app 

**1)** git clone the following repo:

__`❍ git clone https://github.com/supermadu7/project-ml-microservice-kubernetes.git`__

**2)** Enter the following directory:

__`❍ cd project-ml-microservice-kubernetes`__

**3)** Install [python](https://www.python.org/) if not already installed and run this command to create a virtual environment and activate it:

__`❍ make setup`__

**4)** Install the project dependencies:

__`❍ make install`__

**5)** Lint the project files:

__`❍ make lint`__

**6)** Run this script to build a docker image for the app and start the app in a docker container:

__`❍ ./run_docker.sh `__

**7)** Get a prediction from the app running in the Docker container:

__`❍ ./make_prediction.sh `__

**8)** Upload the docker image to your Docker hub account:

__`❍ ./upload_docker.sh `__

**9)** Run the service in a kubernetes cluster.

__`❍ ./run_kubernetes.sh `__

**10)** Get a prediction from the app running in the Kubernetes Cluster after port forwarding is successful:

__`❍ ./make_prediction.sh `__


## Required files

* app.py: This is the flask app that runs the service
* Makefile: This file has make commands that allows for easy setup of a project
* Dockerfile: This file has the setup for creating a Docker image for the microservice
* run_docker.sh: This script creates a docker image from the Dockerfile, list the images and starts a container
* make_prediction.sh: This script sends data for prediction using curl and prints the predicted value on the command line
* upload_docker.sh: This script uploads a docker image to docker hub
* run_kubernetes.sh: This script runs the docker image in a kubernetes cluster
