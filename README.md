[![CircleCI](https://circleci.com/gh/Rushane/Machiine-Learning-Microservice/tree/main.svg?style=svg)](https://circleci.com/gh/Rushane/Machiine-Learning-Microservice/tree/main)

## Project Overview

In this project, you will apply the skills you have acquired in this course to operationalize a Machine Learning Microservice API. 

You are given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests your ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

Your project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project you will:
* Test your project code using linting
* Complete a Dockerfile to containerize this application
* Deploy your containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested

You can find a detailed [project rubric, here](https://review.udacity.com/#!/rubrics/2576/view).

**The final implementation of the project will showcase your abilities to operationalize production microservices.**

---

## Setup the Environment

* Create a virtualenv and activate it
  
  `python3 -m venv ~/.devops`
  
  `source ~/.devops/bin/activate`
  
* Run `make install` to install the necessary dependencies in the virtualenv

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Make predictions:  `./make_prediction.sh`
4. Upload Docker image to Docker hub:  `./upload_docker.sh`
5. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl

### Files
* .circleci/config.yml - This is used for automated deployments in circleci
* output_txt_files - These contain the output of the logs when running the `./run_docker.sh` and `./run_kubernetes.sh`
* Dockerfile - This contains a set of commands that define a python based image.
* Makefile - Contains a set of shell commands that make setup, installation and testing easier.
* run_docker.sh - Shell script that contains the commands to build and run the docker image
* make_prediction.sh - This shell script is responsible for sending input data to the containerized app via the appropriate port which is then used to make the prediction.
* upload_docker.sh - pushes the docker image to docker hub.
* run_kubernetes.sh - Runs the Docker Hub container with kubernetes

