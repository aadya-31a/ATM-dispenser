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
        emailext (
            subject: "SUCCESS: Jenkins Build ${env.BUILD_NUMBER}",
            body: "Build Success\n${env.BUILD_URL}",
            to: "maneesha9391@gmail.com",
            attachLog: true
        )
    }

    failure {
        emailext (
            subject: "FAILED: Jenkins Build ${env.BUILD_NUMBER}",
            body: "Build Failed\n${env.BUILD_URL}",
            to: "maneesha9391@gmail.com",
            attachLog: true
        )
    }

    always {
        echo 'ATM dispensers pipeline completed'
    }
}


}
