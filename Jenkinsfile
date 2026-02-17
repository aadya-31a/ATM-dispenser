pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build started...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
    }

    post {
        success {
            emailext(
                subject: "BUILD SUCCESS: Job Completed",
                body: "Good news! Your Jenkins build finished successfully.",
                to: "maneesha9391@gmail.com"
                attachlog: true
            )
        }
    }
}
