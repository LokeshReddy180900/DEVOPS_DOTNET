pipeline {
    agent any

    stages {
        stage("Building"){
            steps {
                echo "Building SourceCode"
                sh 'dotnetBuild MyWebApp'
                echo "Built Successfully"
            }
        }
    }
}