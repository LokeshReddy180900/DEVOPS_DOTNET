pipeline {
    agent any

    stages {
        stage("Build") {
            steps {
                dir("/var/lib/jenkins/workspace/Dotnet_project/MyWebApp/MyWebApp.csproj") {
                    script {
                        // Build the .NET project
                        sh 'dotnet build'
                    }
                }
            }
        }

        stage("Run") {
            steps {
                dir("/var/lib/jenkins/workspace/Dotnet_project/MyWebApp/MyWebApp.csproj") {
                    script {
                        // Run the .NET application
                        sh 'dotnet run'
                    }
                }
            }
        }
    }
}
