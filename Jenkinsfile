pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/yourusername/yourrepo.git'
            }
        }

        stage('Build and Deploy') {
            steps {
                // Stop and remove old containers (if any)
                sh 'docker-compose down'

                // Build and start containers
                sh 'docker-compose up -d --build'
            }
        }
    }

    post {
        success {
            echo 'Deployment Successful!'
        }
        failure {
            echo 'Deployment Failed! Check logs.'
        }
    }
}