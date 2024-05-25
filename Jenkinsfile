pipeline {
    agent any

    stages {
        stage('Deploy on k8s') {
            steps {
                withCredentials([string(credentialsId: 'minikube_credentials', variable: 'api_token')]) {
                    sh '''
                        echo "Deploying Deployment"
                        kubectl --token $api_token --server https://host.docker.internal:59443 --insecure-skip-tls-verify=true apply -f ./k8s/deployment.yaml --validate=false --v=8
                    '''
                    sh '''
                        echo "Deploying Service"
                        kubectl --token $api_token --server https://host.docker.internal:59443 --insecure-skip-tls-verify=true apply -f ./k8s/service.yaml --validate=false --v=8
                    '''
                }
            }
        }
    }

    post {
        success {
            echo 'Redis deployment completed successfully.'
        }
        failure {
            echo 'Redis deployment failed.'
        }
    }
}
