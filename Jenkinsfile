pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh './build.sh'
            }
        }
        stage('Test') {
            steps {
                sh './run-tests.sh'
            }
        }
        stage('Lint') {
            steps {
                sh './lint.sh'
            }
        }
    }
    post {
        success {
            echo "PR validated successfully!"
        }
        failure {
            echo "PR validation failed successfully!"
        }
    }
}
