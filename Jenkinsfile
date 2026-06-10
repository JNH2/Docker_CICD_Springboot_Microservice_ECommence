pipeline {
    agent any

    stages {
        stage('Test GitHub Webhook') {
            steps {
                echo ' Docker check triggered by GitHub push'
            }
        }

        stage('Check Docker') {
            steps {
                sh 'docker --version'
            }
        }
    }
}
