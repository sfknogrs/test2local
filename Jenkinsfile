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
        sh 'docker run -p 3000:3000 getting-started'
      }
    }
    stage('Verify') {
      steps {
        timeout(time: 10, unit: 'SECONDS') {
          sh 'while ! curl -sSf http://localhost:3000 > /dev/null; do sleep 1; done'
        }
      }
    }
  }
}

