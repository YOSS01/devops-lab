pipeline {
    agent any
    stages {
        stage('Build Docker') {
            steps {
                bat 'docker build -t webapp:latest .'
            }
        }
        stage('Deploy Kubernetes') {
            steps {
                bat 'kubectl apply -f deployment.yaml --validate=false'
                bat 'kubectl apply -f service.yaml --validate=false'
            }
        }
    }
}
