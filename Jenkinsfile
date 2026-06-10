pipeline {
    agent any

    stages {
        stage('Build Jar') {
            steps {
                dir('service-registry') {
                    sh 'chmod +x mvnw'
                    sh './mvnw clean package -DskipTests'
                }
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t service-registry:latest ./service-registry'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    docker rm -f service-registry || true
                    docker run -d --name service-registry -p 8761:8761 service-registry:latest
                '''
            }
        }
    }
}
