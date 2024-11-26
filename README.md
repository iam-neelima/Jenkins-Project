# Jenkins Pipeline for Java Application with Maven, SonarQube, Argo CD, and Kubernetes

This repository demonstrates an end-to-end CI/CD pipeline setup for a Java application using Jenkins, Maven, SonarQube, Argo CD, and Kubernetes. The pipeline automates the process from code checkout to production deployment.

## Prerequisites

- Java application source code hosted on a Git repository.
- Jenkins server with the following plugins installed:
  - Git
  - Maven Integration
  - Pipeline
  - Kubernetes Continuous Deploy
- Kubernetes cluster.
- Argo CD installed on the Kubernetes cluster.

## Pipeline Stages

1. **Code Checkout**: The pipeline fetches the source code from the Git repository.
2. **Build**: The Java application is built using Maven.
3. **Unit Testing**: Unit tests are executed using JUnit.
4. **Code Quality Analysis**: SonarQube analyzes the code quality.
5. **Packaging**: The application is packaged into a JAR file.
6. **Test Environment Deployment**: The application is deployed to a test environment on Kubernetes.
7. **User Acceptance Testing (UAT)**: Automated UATs are run on the deployed application.
8. **Production Deployment**: The application is promoted to production using Argo CD.

## Setup Instructions

1. **Install Necessary Plugins**: Ensure required Jenkins plugins are installed (Git, Maven Integration, Pipeline, Kubernetes Continuous Deploy).
2. **Pipeline Configuration**:
   - Create a Jenkins pipeline job and link it to the Git repository containing the application code.
   - Add a `Jenkinsfile` to the repository to define the pipeline stages.
3. **Argo CD Setup**:
   - Install Argo CD and configure it to track a Git repository containing Kubernetes manifests.
   - Create Kubernetes manifests for the Java application.
   - Add the Argo CD API token to Jenkins credentials for secure integration.
4. **Run the Pipeline**:
   - Trigger the Jenkins pipeline to start the CI/CD process.
   - Monitor stages and resolve any issues.

## Outcome

This pipeline automates the CI/CD workflow for Java applications, leveraging SonarQube for quality checks and Argo CD for deployment and management in Kubernetes.
