pipeline { 
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'nirmal', toolName: 'docker') {
                        sh "docker build -t nirmal/adservice:latest "
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'nirmal', toolName: 'docker') {
                        sh "docker push nirmal/adservice:latest "
                    }
                }
            }
        }
    }
}
