pipeline {
    agent any

    stages {
        stage("Building"){
            steps {
                echo "Building SourceCode"
                bat 'dotnetBuild MyWebApp'
                echo "Built Successfully"
            }
        }
    }
}