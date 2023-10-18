pipeline {
    agent any

    environment {
        dotnet = "/home/ubuntu/.dotnet/dotnet"
        sln = "/home/ubuntu/DEVOPS_DOTNET/MyWebApp"
    }

    stages {
        stage("Building") {
            steps {
                echo "Building SourceCode"
                sh "${dotnet} build ${sln}"
                echo "Built Successfully"
            }
        }
    }
}