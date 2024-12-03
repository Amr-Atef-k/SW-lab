pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        script {
          bat 'dotnet build sw-lab.sln'
        }
      }
    }
    stage('Docker Build') {
      steps {
        script {
          bat 'docker build -t sw-lab-api .'
        }
      }
    }
    stage('Deploy to Staging') {
      steps {
        script {
          bat 'docker-compose up --build -d'
        }
      }
    }
  }
}