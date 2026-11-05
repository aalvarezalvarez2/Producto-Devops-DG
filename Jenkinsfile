pipeline {
    agent { label 'aws-minikube' }

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t miapp:$BUILD_NUMBER .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'kubectl apply -f k8s/'
            }
        }
    }
}
