pipeline {
    agent any

    stages {
        stage('restore') {
            steps {
                powershell 'dotnet restore'
            }
        }
        stage('build') {
            steps {
                powershell 'dotnet build --configuration Release --no-restore'
            }
        }
        stage('package') {
            steps {
                powershell 'Compress-Archive -Path .\\bin\\Release\\net6.0\\ -DestinationPath .\\target.zip'
            }
        }
        stage('onboard') {
            steps {
                testBase useConfigurationFile: true, configurationFilePath: 'TestBase.json'
            }
        }
    }
}