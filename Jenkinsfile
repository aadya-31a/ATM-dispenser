pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Starting build..."
                bat 'echo Building project'
            }
        }
    }

    post {
        always {
            emailext(
                to: "maneesha9391@gmail.com"
               subject: "Build ${currentBuild.currentResult}: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """
Hello Team,

Build Status : ${currentBuild.currentResult}
Job Name     : ${env.ATM-dispensers}
Build No     : ${env.BUILD_NUMBER}
Build URL    : ${env.BUILD_URL}

Please find the build log attached.

Regards,
Jenkins CI
""",
                to: "ATM-dispensers@gmail.com",
                attachLog: true
            )
        }
    }
}
