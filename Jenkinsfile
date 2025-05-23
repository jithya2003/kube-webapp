
pipeline{
    agent any
    stages{
        stage('Clone'){
            steps{
                git branch: 'main', url: 'https://github.com/jithya2003/kube-webapp.git'


            }

        }
        stage('Test'){
            steps{
                echo 'Checking files'
                sh 'ls index.html style.css'
            }
        }
        stage('Build Image'){
            steps{
                script{
                    sh 'docker build -t kube-webapp .'
                }

            }
        }
        stage('Load Image into Minikube'){
            steps{
                sh 'minikube image load kube-webapp'
            }

        }
        stage('Deploy to Kubernetes'){
            steps{
            sh 'kubectl apply -f deployment.yaml'
            }

        }

     }

}

