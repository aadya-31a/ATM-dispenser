pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build running successfully...'
            }
        }
    }

    post {
        success {
            emailext(
                subject: "BUILD SUCCESS",
                body: "Jenkins build completed successfully",
                to: "maneesha9391@gmail.com",
                attachLog: true
            )
        }
    }
}
