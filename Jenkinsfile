pipeline {
    agent any

    environment {
        // Define the Docker image name (can also be a custom-built image)
        DOCKER_IMAGE = 'my-app-image'
        DOCKER_TAG = 'latest'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the repository to get the necessary code
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image from the Dockerfile
                    sh 'docker build -t $DOCKER_IMAGE:$DOCKER_TAG .'
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    // Run a container from the image
                    sh """
                    docker run -d --name my-app-container \
                    -e ENV_VAR=value \
                    $DOCKER_IMAGE:$DOCKER_TAG
                    """
                }
            }
        }

        stage('Test Application') {
            steps {
                script {
                    // Run tests within the Docker container
                    // Example: execute a test command inside the running container
                    sh 'docker exec my-app-container /bin/sh -c "your_test_command"'
                }
            }
        }

        stage('Clean Up') {
            steps {
                script {
                    // Stop and remove the Docker container
                    sh 'docker stop my-app-container'
                    sh 'docker rm my-app-container'
                }
            }
        }
    }

    post {
        always {
            // Clean up Docker images if needed (optional)
            sh 'docker rmi $DOCKER_IMAGE:$DOCKER_TAG || true'
        }
    }
}
