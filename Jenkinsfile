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
                subject: 'Build SUCCESS',
                body: 'Your Jenkins build is successful',
                to: 'maneesha9391@gmail.com',
                attachLog: true
            )
        }

        failure {
            emailext(
                subject: 'Build FAILED',
                body: 'Build failed. Check console.',
                to: 'maneesha9391@gmail.com',
                attachLog: true
            )
        }
    }
}
