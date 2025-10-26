pipeline {
    agent any

    options {
        timestamps()
    }
    stages {
        stage('Checkout') {
            when { branch 'main' }
            steps {
                checkout scm
            }
        }

        stage('Restore') {
            when { branch 'main' }
            steps {
                powershell 'dotnet restore'
            }
        }

        stage('Build') {
            when { branch 'main' }
            steps {
                powershell 'dotnet build --configuration Release --no-restore'
            }
        }

        stage('Test') {
            when { branch 'main' }
            steps {
                powershell 'dotnet test --configuration Release --no-build --logger "trx;LogFileName=test_results.trx"'
            }
        }
    }
}
