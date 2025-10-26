pipeline {
    agent any 
    stages {
        stage('Build project') {
            when { branch 'main' }
            steps {
                bat 'dotnet build'
            }
        }

        stage('Test') {
            when { branch 'main' }
            steps {
                powershell 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}