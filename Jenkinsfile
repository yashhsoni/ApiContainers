pipeline {
  agent any

  environment {
    KUBECONFIG = "${HOME}\\.kube\\config"
  }

  stages {
    stage('Clone Repo') {
      steps {
        git branch: 'main', url: 'https://github.com/yashhsoni/ApiContainers.git'
      }
    }

    stage('Terraform Init') {
      steps {
        bat 'terraform init'
      }
    }

    stage('Terraform Plan') {
      steps {
        bat 'terraform plan'
      }
    }

    stage('Terraform Apply') {
      steps {
        bat 'terraform apply -auto-approve'
      }
    }

    stage('Deploy to AKS') {
      steps {
        bat 'kubectl apply -f Deployment.yml'
      }
    }
  }
}
