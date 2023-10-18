pipeline {
    agent any

    stages {
        stage("Build") {
            steps {
                dir("/var/lib/jenkins/workspace/Dotnet_project/MyWebApp") {
                    script {
                        sh 'dotnet run --project "MyWebApp.csproj"'
                    }
                }
            }
        }
    }
}
