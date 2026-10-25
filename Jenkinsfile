pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out CI/CD project'
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t cicd-web-app:latest .'
            }
        }

        stage('Deploy Application') {
            steps {
                sh 'docker stop cicd-web-app || true'
                sh 'docker rm cicd-web-app || true'
                sh 'docker run -d --name cicd-web-app -p 8081:80 --restart unless-stopped cicd-web-app:latest'
            }
        }

        stage('Verify Deployment') {
            steps {
                sh 'docker ps'
                sh 'curl -fsS http://localhost:8081'
            }
        }
    }
}
