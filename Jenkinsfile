pipeline {
    agent any

    environment {
        // Define Docker Compose path if needed
        COMPOSE_FILE = 'docker-compose.yml'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout your GitHub repository
                git branch: 'main', url: 'https://github.com/<Soujanya-cse>/<https://github.com/Soujanya-cse/DevOps-Assignment>.git'
            }
        }

        stage('Build & Deploy') {
            steps {
                // Stop any running containers and rebuild
                sh 'docker-compose down'
                sh 'docker-compose up -d --build'
            }
        }

        stage('Verify') {
            steps {
                sh 'docker ps'
            }
        }
    }

    post {
        success {
            echo 'Deployment successful! Check frontend and backend URLs.'
        }
        failure {
            echo 'Deployment failed. Check logs in Jenkins console.'
        }
    }
}