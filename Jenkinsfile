pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "suprabhat1234/flask-cicd-app"
    }

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/suprabhatghosh1706-lab/flask-cicd-project'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'sudo docker build -t $DOCKER_IMAGE .'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'sudo docker push $DOCKER_IMAGE'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
            }
        }
    }
}