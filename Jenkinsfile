pipeline {
    agent any

    stages {
        stage('Deployment to kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'kube', namespace: 'webapps', serverUrl: 'https://C91F4A4E78AE5034EFDB25F0929B46AF.gr7.ap-south-1.eks.amazonaws.com']]) {
                sh "kubectl apply -f deployment-service.yml"
               }
            }
        }

         stage('verify deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'kube', namespace: 'webapps', serverUrl: 'https://C91F4A4E78AE5034EFDB25F0929B46AF.gr7.ap-south-1.eks.amazonaws.com']]) {
                sh "kubectl get all -n webapps"

                }}
    }
}}

