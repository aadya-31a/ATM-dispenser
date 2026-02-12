pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Starting build..."
                sh 'echo Building project'
            }
        }
    }

    post {
        always {
            emailext(
                subject: "Build ${currentBuild.currentResult}: ${env.ATM-dispensers} #${env.BUILD_NUMBER}",
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
                to: "maneesha9391@gmail.com",
                attachLog: true
            )
        }
    }
}
