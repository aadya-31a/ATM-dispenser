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
            subject: "Jenkins Build: ${currentBuild.currentResult}",
            body: "Build completed for ATM project",
            to: "maneesha9391@gmail.com"
        )
    }
}

}
