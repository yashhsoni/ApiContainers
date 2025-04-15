pipeline {
  agent any

  environment {
    KUBECONFIG = "$HOME/.kube/config"
  }

  stages {
    stage('Clone Repo') {
      steps {
        git branch: 'main', url: 'https://github.com/yashhsoni/ApiContainers.git'

      }
    }

    stage('Deploy to AKS') {
      steps {
        sh 'kubectl apply -f Deployment.yml'
      }
    }
  }
}
