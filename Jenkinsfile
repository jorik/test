pipeline {
  agent none
  stages {
    stage('Test') {
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
