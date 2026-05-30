pipeline{
    agent any
    
    stages{
        stage('Clone Github Repo'){
            steps{
                git branch: 'main', url: 'https://github.com/harshchaudhary01/Jenkins-react-vite-demo-CI-CD.git'
            }
        }
        stage('Docker Image Build'){
            steps{
                sh 'docker build -t react-vite-image .'
            }
        }
        stage('Deploy to Kubernetes'){
            steps{
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
        stage('Verify Deployment'){
            steps{
                sh 'kubectl get pods'
                sh 'kubectl get svc'
            }
        }
    }
}