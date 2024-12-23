pipeline {
    agent any  // Defines where the pipeline should run (e.g., on any available agent)

    environment {
        // Define environment variables if needed
        MY_VAR = 'value'
    }

    stages {
        stage('Build') {
            steps {
                script {
                    // Commands to build your project (e.g., Maven, Gradle, etc.)
                    echo 'Building the project...'
                    sh 'make build'  // Replace with your build commands
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Commands to run tests (e.g., unit tests, integration tests)
                    echo 'Running tests...'
                    sh 'make test'  // Replace with your test commands
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Commands to deploy your project
                    echo 'Deploying the project...'
                    sh 'make deploy'  // Replace with your deploy commands
                }
            }
        }
    }

   
