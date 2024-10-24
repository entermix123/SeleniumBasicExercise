pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Run TestProject1 Tests') {
            steps {
                echo 'Running TestProject1 tests'
                bat 'dotnet test TestProject1/TestProject1.csproj --verbosity normal'
            }
        }

        stage('Run TestProject2 Tests') {
            steps {
                echo 'Running TestProject2 tests'
                bat 'dotnet test TestProject2/TestProject2.csproj --verbosity normal'
            }
        }

        stage('Run TestProject3 Tests') {
            steps {
                echo 'Running TestProject3 tests'
                bat 'dotnet test TestProject3/TestProject3.csproj --verbosity normal'
            }
        }
    }
}
