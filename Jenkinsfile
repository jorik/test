pipeline {
  agent none
  stages {
    stage('Test') {
      
      agent {
        docker {
          image 'microsoft/dotnet:sdk' 
        }
      }
      
      steps {
        sh 'dotnet --version'
      }
    }
    
    stage('Build dockerfile') {
      agent any
      steps {
        sh 'docker build -t jorik/webtest:latest .'
      }
    }
  }
}
