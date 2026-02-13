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
                subject: "SUCCESS: Job ${env.ATM-dispensers}",
                body: "Build Success 😊\nJob: ${env.ATM-dispenser}\nBuild: ${env.BUILD_NUMBER}",
                to: "maneesha9391@gmail.com",
                attachLog: true
            )
        }

        failure {
            emailext(
                subject: "FAILED: Job ${env.ATM-dispenser}",
                body: "Build Failed ❌",
                to: "maneesha9391@gmail.com",
                attachLog: true
            )
        }
    }
}
