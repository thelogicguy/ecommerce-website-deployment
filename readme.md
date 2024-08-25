# E-commerce Website Deployment using Jenkins and Docker

This README provides a detailed guide on deploying an e-commerce website using Jenkins with both Freestyle and Pipeline jobs, Docker, and Docker Hub. The process covers creating a Dockerfile, building an NGINX image, pushing the image to Docker Hub, and running a Docker container.

## Prerequisites
Before starting, ensure you have the following installed and configured:

- Jenkins (with necessary plugins: Git, Docker Pipeline, Credentials Binding)
- Docker (installed on the Jenkins server)
- GitHub Account
- Docker Hub Account

### Step-by-Step Process

1. Setting Up Jenkins
- Install Jenkins:

- Download and install Jenkins on your preferred server.
- Access Jenkins at http://<your-server-ip>:8080.
- Install Required Plugins:

- Navigate to Manage Jenkins > Manage Plugins.
- Install the following plugins:
- Git Plugin
- Docker Pipeline Plugin
- Credentials Binding Plugin

2. Preparing the Docker Environment
- Create a Dockerfile:
- In your local development environment, create a Dockerfile for NGINX
- Ensure that the index.html file is in the same directory as the Dockerfile.
- Push the Dockerfile to GitHub:

- Create a new repository on GitHub.
- Push your Dockerfile and index.html to the repository.

3. Creating Jenkins Jobs
A. Freestyle Job
- Create Freestyle Job:

- Go to Jenkins Dashboard > New Item.
- Select Freestyle project, name it ecommerce-freestyle-deploy, and click OK.
- Configure Source Code Management:

- Under Source Code Management, select Git.
- Provide the repository URL and credentials.
- Add Build Steps:

- Under Build, click Add build step > Execute shell
- Save and Build:

- Save the configuration and click Build Now to deploy the e-commerce site.

B. Pipeline Job
- Create Pipeline Job:

- Go to Jenkins Dashboard > New Item.
- Select Pipeline, name it ecommerce-pipeline-deploy, and click OK.
- Configure Source Code Management

- Under Pipeline, select Pipeline script from SCM.
- Choose Git, provide the repository URL, and specify the branch.
- Define the Pipeline Script
- Save and Build

Save the pipeline and click Build Now to start the deployment.
4. Accessing the Deployed Website
- After the build completes, access the e-commerce website at http://<your-server-ip>:8081.
