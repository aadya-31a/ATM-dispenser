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
    always {
        emailext (
            to: 'maneesha9391@gmail.com',
            subject: "Build Status: ${currentBuild.currentResult}",
            body: "Check attached build log",
            attachLog: true
        )
    }
}
}
