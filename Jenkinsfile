pipeline {
    agent any 
    stages {
        stage('Build project') {
            steps {
                bat 'dotnet build'
            }
        }

        stage('Test') {
            steps {
                powershell 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}