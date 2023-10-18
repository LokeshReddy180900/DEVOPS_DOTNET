pipeline {
    agent any

    stages {
        stage("Build") {
            steps {
                dir("/var/lib/jenkins/workspace/Dotnet_project/MyWebApp") {
                    script {
                        sh '/usr/lib/dotnet/sdk/7.0.112/MSBuild.dll -maxcpucount -verbosity:m -restore -consoleloggerparameters:Summary --project "MyWebApp.csproj"'
                    }
                }
            }
        }
    }
}
