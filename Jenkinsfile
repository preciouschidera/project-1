pipeline {
  agent any

  stages {
    stage('Clone Repo') {
      steps {
        git branch: 'main', url: 'https://github.com/preciouschidera/project-1.git'
      }
    }

    stage('Build Docker Image') {
      steps {
        script {
          docker.build("leocrita/calculator-app:latest")
        }
      }
    }

    stage('Run Docker Container') {
      steps {
        script {
          docker.image("leocrita/calculator-app:latest").run("-d -p 8081:8080")
        }
      }
    }

    stage('Push Docker Image') {
      steps {
        script {
          docker.withRegistry('https://index.docker.io/v1/', 'docker-hub-creds') {
            docker.image("leocrita/calculator-app:latest").push()
          }
        }
      }
    }
  }
}
