pipeline {
    agent any

    stages {
        stage("Build") {
            steps {
                dir("/var/lib/jenkins/workspace/Dotnet_project/MyWebApp") {
                    script {
                        // Build the .NET project
                        sh 'dotnet build --project "MyWebApp.csproj"'
                    }
                }
            }
        }

        stage("Run") {
            steps {
                dir("/var/lib/jenkins/workspace/Dotnet_project/MyWebApp") {
                    script {
                        // Run the .NET application
                        sh 'dotnet run --project "MyWebApp.csproj"'
                    }
                }
            }
        }
    }
}
