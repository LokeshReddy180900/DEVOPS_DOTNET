pipeline {
    agent any

    environment {
        MSBuildSDKsPath = '/usr/lib/dotnet/sdk/7.0.112/Sdks'
    }

    stages {
        stage("Build") {
            steps {
                dir("/var/lib/jenkins/workspace/Dotnet_project/MyWebApp") {
                    script {
                        sh 'dotnet build --project "MyWebApp.csproj"'
                    }
                }
            }
        }
    }
}
