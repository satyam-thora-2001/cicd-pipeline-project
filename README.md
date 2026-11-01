End-to-End CI/CD Pipeline Project

Project Overview

This project demonstrates an automated CI/CD pipeline using Jenkins, Docker, GitHub, and AWS EC2.

The application is built and deployed automatically through Jenkins Pipeline.

Technologies Used

- AWS EC2
- Ubuntu Linux
- Jenkins
- Docker
- GitHub
- Nginx
- HTML

Project Architecture

Developer → GitHub → Jenkins → Docker Build → Docker Container → AWS EC2 → Browser

Project Structure

cicd-pipeline-project/
│
├── Dockerfile
├── Jenkinsfile
├── README.md
└── index.html

CI/CD Pipeline Stages

1. Checkout SCM – Fetch source code from GitHub.
2. Build Docker Image – Build application image using Dockerfile.
3. Deploy Application – Run the Docker container.
4. Verify Deployment – Verify application using curl.

Dockerfile

FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
EXPOSE 80

Pipeline Result

- Jenkins Pipeline executed successfully.
- Docker image built successfully.
- Application deployed on AWS EC2.
- Application verified through browser.

Author

Satyam Thorat




