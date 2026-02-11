pipeline {
agent any

```
stages {
    stage('Build') {
        steps {
            echo 'Build triggered from GitHub push 🚀'
        }
    }
}

post {
    always {
        emailext(
            to: 'maneesha9391@gmail.com',
            subject: "Jenkins Build Notification",
            body: """Hello Maneesha,
```

Build Status: ${currentBuild.currentResult}
Job Name: ${env.JOB_NAME}
Build Number: ${env.BUILD_NUMBER}

Check console:
${env.BUILD_URL}

Thank you"""
)
}
}
}
