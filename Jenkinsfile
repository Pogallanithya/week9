pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t registration:v1 .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                bat 'docker tag registration:v1 pogallanithya/registration:v1'
                bat 'docker push pogallanithya/registration:v1'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f C:/1279/deployment.yaml'
                bat 'kubectl apply -f C:/1279/service.yaml'
            }
        }
    }
}
