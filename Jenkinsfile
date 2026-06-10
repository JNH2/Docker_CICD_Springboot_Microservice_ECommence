pipeline {
    agent any

    stages {

        stage('Check Docker') {
            steps {
                sh 'docker --version'
            }
        }

        stage('Build Service Registry') {
            steps {
                sh 'docker build -t service-registry:latest ./service-registry'
            }
        }

    }
}
