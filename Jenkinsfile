pipeline {
    agent {
        docker { image ''microsoft/dotnet:2.1-sdk }
    }
    stages {
        stage('Test') {
            steps {
                sh 'dotnet --version'
            }
        }
    }
}
