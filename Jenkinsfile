pipeline {
  agent any
  environment {
    IMAGENAME = "devopstestjenkins"
  
  }
  stages {
    stage('Docker Build') {
      steps {
        sh 'git clone https://github.com/docker/getting-started.git'
        sh 'docker build -t getting-started .'
        sh 'docker run -d -p 3000:3000 getting-started'
        
      }
    }
    stage('Terraform') {
      steps {
        sh 'terraform version'
        sh 'terraform init'
        sh 'terraform plan'
        sh 'terraform apple -auto-approve'
        sh 'terraform output'
      }
    } 
  }   
}
