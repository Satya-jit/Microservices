pipeline {
    agent any

    stages {
        stage('Deploy to Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://4C89B2CC5EE79896D8A3FCA138DFC6E1.gr7.us-east-1.eks.amazonaws.com']]) {
                   sh "kubectl apply -f deployment-service.yml"
              }
            }
        stages {
        stage('verify deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://4C89B2CC5EE79896D8A3FCA138DFC6E1.gr7.us-east-1.eks.amazonaws.com']]) {
                   sh "kubectl get all -n webapps"
              }
           }
    }
}
