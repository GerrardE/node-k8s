# node-k8s

[![CircleCI](https://circleci.com/gh/GerrardE/node-k8s/tree/main.svg?style=svg)](https://circleci.com/gh/GerrardE/node-k8s/tree/main)

## Getting Started

This repo contains a simple web application that runs an api(GET/POST) request and prints the request header, method, and body. 

It is integrated with CircleCI CI/CD.

## Required Technologies

This application makes use of the following technologies:

- [Typescript](https://www.typescriptlang.org/) for Javascript type safety
- [Node](https://nodejs.org/) for creating the APIs
- [Circle CI](https://circleci.com/) for continuous integration and delivery
- [Helm](https://helm.sh/docs/intro/quickstart/) for kube manifest management
- [Docker](https://docs.docker.com/get-started/) for containerizing the application
- [Kubernetes](https://kubernetes.io/docs/) for container orchestration

## Installation

### 1. Installation Steps

These instructions assumes that you have a working installation of `git`, `docker`, `docker-compose`, `helm`, `minikube` and `nodejs`. See the instructions for installation:

- [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) 
- [Docker](https://docs.docker.com/get-docker/)
- [Docker-compose](https://docs.docker.com/compose/install/)
- [Helm](https://helm.sh/docs/intro/install/)
- [Minikube](https://minikube.sigs.k8s.io/docs/start/)
- [Node](https://nodejs.org/en/download/)

Provision the necessary services needed for running the application locally:

1. Clone this repository to your PC and 
1. Run `yarn` or `npm install` in the root folder to install dependencies
1. Make a copy of the `.env.example` file to `.env` in the root of the project
1. Run `yarn build` or `npm run build` in the root folder to run build
1. Run `yarn test` or `npm test` in the root folder to run api tests
1. Run `yarn start` or `npm start` or `docker-compose up` in the root folder to start the api
1. The endpoints can be hit using the following format:

   ```
   curl --header "Content-Type: application/json" --data '{"username":"xyz","password":"xyz"}' `http://localhost:<PORT>`
   ```

   App Endpoints:

   ```
   POST endpoint - `http://localhost:<PORT>`
   GET endpoint - `http://localhost:<PORT>`
   GET metrics endpoint - `http://localhost:<PORT>/metrics`
   ```

   Or test the endpoints using Postman.

1. To deploy the application to a local minikube cluster, you need to first spin up the minikube environment using `minikube start` or:
- Visit [Kubernetes](https://kubernetes.io/docs/tutorials/hello-minikube/) an launch a new terminal
- Run `sudo snap install helm --classic` to install `helm`
- Clone this repository `https://github.com/GerrardE/node-k8s.git` and `cd node-k8s`

1. From the root of the directory, deploy the manifest files using `helm install node-k8s node-k8s-0.1.0.tgz`
1. Run `kubectl get all` to review resources deployed.
