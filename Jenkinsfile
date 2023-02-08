pipeline {
  agent any
  environment {
    IMAGENAME = "devopstestjenkins"
  
  }
  stages {
    stage('Docker Build') {
      steps {
        sh 'docker images'
        sh 'docker build -t getting-started .'
        sh 'docker images'
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
