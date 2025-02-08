pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                echo "Username: ${params.USERNAME}"
                echo "Deploy: ${params.DEPLOY}"
                echo "Environment: ${params.ENVIRONMENT}"
                bat 'echo Starting Hello World Pipeline'
                bat 'javac Hello.java'
                }
            }
        }

        stage('Execute Script') {
            steps {
                script {
                    bat 'java Hello'
                }
            }
        }
    }
}
