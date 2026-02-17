pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building project..."
            }
        }
    }

    post {
        success {
            emailext (
                to: 'maneesha9391@gmail.com',
                subject: "Build SUCCESS: ${env.JOB_NAME}",
                body: "Build completed successfully."
                attchLog: true
            )
        }

        failure {
            emailext (
                to: 'maneesha9391@gmail.com',
                subject: "Build FAILED: ${env.JOB_NAME}",
                body: "Build failed. Check Jenkins."
                attchLog: true
            )
        }
    }
}
