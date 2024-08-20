**Streamlined CI/CD Pipeline for Web Development using Jenkins, Git, and Docker**

Project Overview
This project demonstrates setting up a Continuous Integration/Continuous Deployment (CI/CD) pipeline for a simple web application. The pipeline automates building, testing, and deploying the app using Jenkins, GitHub, and Docker.

Technologies Used
Jenkins
Git & GitHub
Docker & NGINX
EC2 Linux (Jenkins & Docker setup)

Key Achievements:
Automated the software development lifecycle.
Improved deployment efficiency and reduced manual errors.
Deployed a web app using Docker with NGINX as a web server.

Prerequisites
Development Environment:
Git, Jenkins, Docker installed on EC2 Linux instance.
Open ports 8080 and 8081 in your security group settings.
GitHub Repository: Jenkins-CI-CD-Pipeline-for-a-Web-Application

Setup Instructions
Step 1: Clone the Repository
git clone https://github.com/Sandhyagito/Jenkins-CI-CD-Pipeline-for-a-Web-Application.git

Step 2: Create a Simple Web Application
Create an index.html file in your cloned repository with basic content.

Step 3: Set Up Jenkins on an EC2 Instance
Follow these steps:

Install Jenkins and Docker.
Configure Jenkins to use Docker.
Set up necessary security group rules.
Step 4: Jenkins Pipeline Configuration
In Jenkins:

Create a new pipeline project.
Use the following pipeline script:

pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Sandhyagito/Jenkins-CI-CD-Pipeline-for-a-Web-Application.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                script {
                    sh '''
                        docker run --name Sandhya-Webserver -d -p 8081:80 -v "$(pwd):/usr/share/nginx/html" nginx
                    '''
                }
            }
        }
    }
}
Step 5: Access the Deployed Web Application
Access the application via http://<your-ec2-public-ip>:8081

![Picture1](https://github.com/user-attachments/assets/f8efb0e9-2fce-4d30-b986-e7a90f061824)

![Picture2](https://github.com/user-attachments/assets/d1097ac1-e0f2-4978-8f83-2cc5639b670b)

![image](https://github.com/user-attachments/assets/c6234f59-542e-43ed-859a-153b141e0542)

This project successfully demonstrates your ability to build and deploy a web application using a CI/CD pipeline with Jenkins and Docker.

Outcome:
•	NGINX will start within the container and serve the contents of your index.html file.
•	You can access your web application via http://<your-ec2-public-ip>:8080 in your browser.
In summary, this command spins up a Docker container running NGINX that serves your web application.
