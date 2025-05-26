pipeline {
    agent any

    environment {
        IMAGE_NAME = "calculator-app"
        CONTAINER_NAME = "calculator-container"
        PORT = "8080"
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'project-1', url: 'https://github.com/DebbieAmus/proj-mdp-152-155.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh """
                    docker build -t ${IMAGE_NAME}:latest .
                    """
                }
            }
        }

        stage('Stop Existing Container') {
            steps {
                script {
                    sh """
                    docker stop ${CONTAINER_NAME} || true
                    docker rm ${CONTAINER_NAME} || true
                    """
                }
            }
        }

        stage('Run New Container') {
            steps {
                script {
                    sh """
                    docker run -d --name ${CONTAINER_NAME} -p ${PORT}:8080 ${IMAGE_NAME}:latest
                    """
                }
            }
        }
    }

    post {
        success {
            echo "🚀 App deployed! Access it at http://3.137.186.216:${PORT}/app/"
        }
        failure {
            echo "❌ Build or deployment failed!"
        }
    }
}
