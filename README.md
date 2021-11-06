# Status Badge

[![acholonu](https://circleci.com/gh/acholonu/udacity_project4_submission.svg?style=svg)](https://app.circleci.com/pipelines/github/acholonu/udacity_project4_submission)

## Summary

The purpose of this project is to run a housing prediction app within a docker container.
After building the container with no error, we then want to try and run this containerized app
on kubernetes.

## How to Run

Please run the following shell commands to run this project:

### To run containerized app and then make a prediction

1. `./run_docker.sh`
2. In another shell window: `./make_prediction.sh`

### To run the containerized app using kubernetes

1. Upload container to repository: `./upload_docker.sh`
2. `run_kubernetes.sh`
3. In another terminal/shell window: `./make_predictions.sh`
4. To see the logs type: `kubectl logs house-predictions`

## Key Files in The Repository

In order of appearance.

1. **.circleci/config.yml**: configures the CICD pipeline for building, installing dependency, and linting code and dockerfile.
2. **app.py**: Flask app that has a housing app prediction.
3. **docker_out.txt**: Output from running a predictions for the docker container.
4. **Dockerfile**: Docker file to build the container that runs the flask app (i.e., app.py).
5. **kubernetes_out.txt**: Output from running a prediction using kubernetes.
6. **make_prediction.sh**: Given document.  Sample input values to use in flask.app to produce a prediction.
7. **Makefile**: a bundle of commands that builds, installs dependencies, and lints application and Dockerfile.
8. **requirements.txt**: lists the python packages that the application needs to run.
9. **run_cleanup.sh**: Cleans up kubernetes clusters.
10. **run_docker.sh**: Create a containers that runs the flask app (i.e., app.py).
11. **run_kubernetes.sh**: Runs the containerized app on a kubernetes cluster
12. **upload_docker**: Uploads images with flask app to docker hub.

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
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl
