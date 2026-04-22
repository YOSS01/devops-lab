pipeline {
    agent any
    environment {
        KUBECONFIG = 'C:\\ProgramData\\Jenkins\\.jenkins\\.kube\\config'
    }
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