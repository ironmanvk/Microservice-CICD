pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps { 
                script {
                    dir('src') {

                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker build -t vamsi537/cartservice:latest ."
                    }
                        }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker push vamsi537/cartservice:latest "
                    }
                }
            }
        }
    }
}
