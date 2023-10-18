pipeline {
    agent any

    /*environment {
        
    } */

    stages {
        stage("Building") {
            steps {
                echo "Building SourceCode"
                sh 'dotnet run'
                echo "Built Successfully"
            }
        }
    }
}