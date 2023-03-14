pipeline {
  agent {
    docker {
      image 'node:14'
      args '-p 4000:3000'
    }
  }
  stages {
    stage('Build') {
      steps {
        git 'https://github.com/sfknogrs/test2local.git'
        sh 'npm install'
        sh 'npm run build'
      }
    }
    stage('Dockerize') {
      steps {
        sh 'docker build -t getting-started .'
        sh 'docker run -p 4000:3000 getting-started'
      }
    }
  }
}
