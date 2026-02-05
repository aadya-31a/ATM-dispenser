pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/aadya-31a/ATM-dispenser.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }
    }

    post {
        always {
            emailext(
                subject: "ATM Jenkins Build Success",
                body: "Build completed successfully from Jenkins",
                to: "maneesha9391@gmail.com",
                from: "maneesha9391@gmail.com"
            )
        }
    }
}
