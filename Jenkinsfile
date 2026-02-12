pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Starting build...'
                bat 'echo Building project'
            }
        }
    }

    post {
        always {
            script {
                emailext(
                    subject: "Build ${currentBuild.currentResult}: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                    body: """Job: ${env.JOB_NAME}
Build Number: ${env.BUILD_NUMBER}
Status: ${currentBuild.currentResult}""",
                    to: 'ATM-dispensers@gmail.com'
                )
            }
        }
    }
}

