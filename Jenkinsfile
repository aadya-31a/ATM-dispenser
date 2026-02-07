pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build triggered from GitHub push 🚀'
            }
        }
    }

    post {
        success {
            emailext(
                subject: "✅ SUCCESS: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """Build Successful 🎉

Job: ${env.JOB_NAME}
Build Number: ${env.BUILD_NUMBER}
Build URL: ${env.BUILD_URL}""",
                to: "maneesha9391@gmail.com"
            )
        }

        failure {
            emailext(
                subject: "❌ FAILED: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """Build Failed ❌
Check console: ${env.BUILD_URL}""",
                to: "maneesha9391@gmail.com",
                attachLog: true
            )
        }
    }
}
