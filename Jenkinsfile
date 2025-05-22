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
          docker.build("calculator-app:latest")
        }
      }
    }

    stage('Run Docker Container') {
      steps {
        script {
          docker.image("calculator-app:latest").run("-d -p 8080:8080")
        }
      }
    }
  }
}
