pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/docker/getting-started.git'
      }
    }
    stage('Build') {
      steps {
        sh 'docker build -t getting-started .'
      }
    }
    stage('Run') {
      steps {
        sh 'docker run -p 4000:3000 getting-started'
      }
    }
  }
}

