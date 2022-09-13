# DevOps Assignment

## The Project

This Gradle project is a simple web application that displays the message "I'm running on X" where X is property depenind on which
Spring Profile is active

### Running locally

Requirements: Java 8+. The project can be run locally with ```./gradlew bootRun --args='--spring.profiles.active=local'``` with the
application being available on ```localhost:8080``` where a message with be shown saying "I'm running on Local"

### Spring Profiles

#### local : done

#### production : got no free to account to deploy on cloud

## Task 1

Create a Bitbucket Pipeline to successfully dockerize the given Java Spring Boot application and deploy the image to Docker Hub.

### Steps taken

1. Created a docker file in the project directory to run the given command: ```./gradlew bootRun --args='--spring.profiles.active=local'```
2. Created a docker image
3. Pushed thus made docker image to docker hub [rangermohit/devops_assignment (tag: 6483f079dfb3a6301b26dbb2a5750e02d296cb18)]

## Task 2

Continue the same Bitbucket Pipeline to deploy the project to production on a Kubernetes instance in any cloud environment (preferably
Google Cloud).

Once deployed, the Kubernetes instance should show an index page with "I’m running on Production", where 'Production' is an app
property set in the respective configuration file.

If using Google Cloud, for Bitbucket to be able to deploy you will need to create a Service Account in the Google Cloud project.

### Steps taken (to deploy locally)

1. Pushed the project directory to bitbucket (https://bitbucket.org/mohitsv/devops_assignment)
2. Enabled bitbucket-pipelines (needs 2-step verification)
3. Created bitbucket-pipeline yaml file to run the pipeline (to do login-build-push for autoupdating the image on docker hub)

4. Enabled Kubernetes on Docker desktop or minikube
5. Created a Kubernetes yaml file to deploy and launch the service (Java scripts)
6. Locally launched the service by applying the Kubernetes yaml file and later using port-forwarding

alternatively...

5. Created a Kubernetes yaml file to deploy, launch the service (Java scripts) and initialize ingress
6. Import ingress on the platform of choice (Docker desktop or minikube)
7. Locally launched the service by applying the Kubernetes yaml file

## Delivering the solutions

The modified project can be shared as an attachment, or via an online repository like GitHub or BitBucket. We will check the
bitbucket-pipelines.yaml file and any other scripts needed to run the pipeline.
