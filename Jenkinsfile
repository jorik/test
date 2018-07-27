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
    
   stage('Docker Push') {
      agent any
      steps {
        withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUser')]) {
          sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
          sh 'docker push jorik/webtest:latest'
        }
      }
    
  }
}
