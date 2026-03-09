pipeline {
  agent any

  stages {

    stage('Clone') {
      steps {
        git 'https://github.com/SoumiMitra2020/DevOps-Project-2026.git'
      }
    }

    stage('Build Docker Image') {
      steps {
        sh 'docker build -t USERNAME/devops-demo .'
      }
    }

    stage('Push Image') {
      steps {
        sh 'docker push USERNAME/devops-demo'
      }
    }

    stage('Deploy to Kubernetes') {
      steps {
        sh 'kubectl apply -f k8s/'
      }
    }
  }
}
