pipeline {
    agent any
    triggers {
        cron('* * * * *')  // Corrected cron expression without extra space
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
