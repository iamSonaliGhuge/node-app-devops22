# node-app-devops22
## Overview
This project shows how to set up a simple CI/CD pipeline for a Node.js app using Jenkins on AWS EC2. Whenever code is pushed to GitHub, Jenkins automatically builds and deploys the new version to the server. This helps keep the app updated easily and makes the deployment process faster.

## Tools and Technologies
Jenkins – For CI/CD automation

GitHub – Source code repository

AWS EC2 – Hosting the application

Node.js – Backend application

Git – Version control

Setup Steps

## 🔹 Step 1: Launch EC2 Instances
![](./image/instance.png)

## 🔹 Step 2: Configure Deployment Server
Run the following commands on the deployment server:

sudo apt update
sudo apt install nodejs -y
sudo apt install npm -y
sudo npm install -g pm2

PM2 helps to keep the app running all the time, even after the server restarts.

## 🔹 Step 3: Push Code to GitHub
Create a new GitHub repository for your project.

Add all your project files including app.js and Jenkinsfile.

Commit and push the code to GitHub.
![](./image/Screenshot%20(37).png)

## 🔹 Step 4: Configure Jenkins Server
Install Jenkins on the Jenkins EC2 instance.

Open Jenkins: http://:8080

Install plugins: Git, Pipeline, SSH Agent

Add credentials for:

GitHub (if private)

Deployment server (SSH key)
![](./image/creditional.png)

## 🔹 Step 5: Create Jenkins Pipeline
In Jenkins, create a new Pipeline job.

Select "Pipeline script from SCM".

Enter your GitHub repository URL.

Save the configuration.

![](./image/jenkinpipeline.png)

## Step 6: Run the Pipeline
Click Build Now in Jenkins.

Jenkins will:

Pull the latest code from GitHub

Connect to the Deployment Server via SSH

Deploy and start the Node.js app using PM2
![](./image/nodeapp.png)

## Results / Output
After running the pipeline:

Jenkins pulled the latest code from GitHub.

Connected to the Deployment Server and deployed the Node.js app using PM2.

The app runs successfully, showing this output in the browser.
![](./image/result.jpeg)

## Conclusion
This project shows a simple CI/CD setup using Jenkins for a Node.js app on AWS. The pipeline automates deployment, keeping the app updated easily and reliably.

