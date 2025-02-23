pipeline {
  agent any
  stages {
    stage('Clone Repository') {
      steps {
        git branch: 'main', url:'https://github.com/lisha-0610/nginx-deploy.git'
      }
    }
    stage('Build Docker Image') {
      steps {
        script{
          sh 'dockers stop nginx-container || true'
          sh 'docker rm nginx-container || true'
          sh 'docker run -d --name nginx-container -p 8080:80 nginx-app'
        }
      }
    }
  }
}
