pipeline {
    agent any

    /*environment {
        
    } */

    stages {
        stage("Building") {
            steps {
                echo "Building SourceCode"
                sh 'dotnetBuild --project /var/lib/jenkins/workspace/Dotnet_project/MyWebApp/MyWebApp.csproj'
                echo "Built Successfully"
            }
        }
    }
}