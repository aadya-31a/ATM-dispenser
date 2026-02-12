pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build running...'
            }
        }
    }

    post {
        success {
            emailext(
                subject: "SUCCESS: Job ${env.JOB_NAME}",
                body: "Build Success 😊\nJob: ${env.JOB_NAME}\nBuild: ${env.BUILD_NUMBER}",
                to: "maneesha9391@gmail.com",
                attachLog: true
            )
        }

        failure {
            emailext(
                subject: "FAILED: Job ${env.JOB_NAME}",
                body: "Build Failed ❌",
                to: "maneesha9391@gmail.com",
                attachLog: true
            )
        }
    }
}
