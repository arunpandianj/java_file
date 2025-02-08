pipeline {
    agent any
    options {
        timeout(time: 5, unit: 'MINUTES')       // Pipeline will timeout after 5 minutes
        retry(2)                                // Retry the pipeline twice if it fails
        timestamps()                            // Add timestamps to console output
        disableConcurrentBuilds()               // Prevent concurrent builds
    }
    parameters {
        string(name: 'USERNAME', defaultValue: 'guest', description: 'Enter your username')
        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Deploy after build?')
        choice(name: 'ENVIRONMENT', choices: ['dev', 'staging', 'prod'], description: 'Select environment')
    }
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
