pipeline {
    agent any

    stages {
       stage('Build') {
    steps {
        bat 'mvn clean install'
    }
}

    }

    post {
        always {
            echo 'ATM dispensers pipeline completed'
        }
    }
}
