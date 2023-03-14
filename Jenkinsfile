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
        git 'https://github.com/your-repo/your-project.git'
        sh 'npm install'
        sh 'npm run build'
      }
    }
    stage('Dockerize') {
      steps {
        sh 'docker build -t your-project .'
        sh 'docker run -p 3000:3000 your-project'
      }
    }
  }
}
