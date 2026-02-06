pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/aadya-31a/ATM-dispenser.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }
    }

    post {
        success {
            emailext(
                to: 'maneesha9391@gmail.com',
                subject: 'Jenkins Build SUCCESS',
                body: 'Build completed successfully'
            )
        }

        failure {
            emailext(
                to: 'maneesha9391@gmail.com',
                subject: 'Jenkins Build FAILED',
                body: 'Build failed. Check Jenkins'
            )
        }
    }
}
