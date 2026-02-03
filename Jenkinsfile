pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                dir('src/ATM-dispensers') {
                    bat 'mvn clean install'
                }
            }
        }
    }

    post {
        always {
            echo 'ATM dispensers pipeline completed'
        }
    }
}
