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
                to: 'maneesha9391@gmail.com',
                subject: 'Build SUCCESS',
                body: 'Your Jenkins build completed successfully'
            )
        }
        failure {
            emailext(
                to: 'maneesha9391@gmail.com',
                subject: 'Build FAILED',
                body: 'Build failed. Check Jenkins.'
            )
        }
    }
}
