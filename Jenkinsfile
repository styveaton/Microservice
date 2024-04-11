pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cre', toolName: 'docker') {
                        sh "docker build -t aton85/currencyservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cre', toolName: 'docker') {
                        sh "docker push aton85/currencyservice:latest "
                    }
                }
            }
        }
    }
}
