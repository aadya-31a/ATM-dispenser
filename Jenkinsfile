pipeline {
    agent any

    stages {
         stage('Build') {
            steps {
                echo 'Starting build...'
                sh 'mvn clean install'
            }
        }
    }

    post {
        always {
            echo 'ATM dispensers pipeline completed'
        }

        success {
            emailext(
                subject: 'Build Success',
                body: 'Your Jenkins build was successful',
                to: 'maneesha9391@gmail.com'
            )
        }

        failure {
            emailext(
                subject: 'Build Failed',
                body: 'Your Jenkins build failed',
                to: 'maneesha9391@gmail.com'

                attachlog: true
            )
        }
    }
}
