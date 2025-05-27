pipeline {
  agent any

  stages {
    stage('Clone Repo') {
      steps {
        git branch: 'project-3', url: 'https://github.com/preciouschidera/project-1.git'
      }
    }

    stage('Deploy to Kubernetes') {
      steps {
          sh 'kubectl apply -f calculator-deployment.yaml'
          sh 'kubectl apply -f calculator-service.yaml'
        }
      }
    }

