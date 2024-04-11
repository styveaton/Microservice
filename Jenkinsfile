pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cre', toolName: 'docker') {
                        sh "docker build -t aton85/frontend:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cre', toolName: 'docker') {
                        sh "docker push aton85/frontend:latest"
                    }
                }
            }
        }
    }
}
