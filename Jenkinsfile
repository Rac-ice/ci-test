pipeline {
    agent any

    environment {
        DOTNET_ROOT = '/usr/share/dotnet'
        ASPNETCORE_ENVIRONMENT = 'Production'
    }

    stages {
        // stage('Run') {
        //     steps {
        //         sh 'dotnet run'
        //     }
        // }
        // stage('Checkout') {
        //     steps {
        //         checkout scm
        //     }
        }
        stage('Restore') {
            steps {
                sh 'dotnet restore'
            }
        }
        stage('Build') {
            steps {
                sh 'dotnet build --configuration Release'
            }
        }
        stage('Test') {
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
        stage('Publish') {
            steps {
                sh 'dotnet publish --configuration Release --output ./publish'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy step - add your deployment scripts here'
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}