pipeline {
  agent any
  stages {
    stage('Build Docker Image') {
      steps {
        sh 'docker build -t portfolio-jenkins:latest .'
      }
    }
    stage('Deploy Container') {
      steps {
        sh 'docker stop portfolio-jenkins || true'
        sh 'docker rm portfolio-jenkins || true'
        sh 'docker run -d --name portfolio-jenkins -p 80:80 portfolio-jenkins:latest'
      }
    }
  }
}
