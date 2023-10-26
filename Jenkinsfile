pipeline {
    agent any

    stages {
        stage("Restore") {
            steps {
                dir("/var/lib/jenkins/workspace/Dotnet_project/MyWebApp") {
                    script {
                        // Restore the dependencies
                        sh 'dotnet restore'
                    }
                }
            }
        }

        stage("Build") {
            steps {
                dir("/var/lib/jenkins/workspace/Dotnet_project/MyWebApp") {
                    script {
                        // Build the .NET project
                        sh 'dotnet build'
                    }
                }
            }
        }

        stage("SonarQube Analysis") {
            steps {
                withSonarQubeEnv('SonarQube Scanner') {
                    dir("/var/lib/jenkins/workspace/Dotnet_project/MyWebApp") {
                        sh 'dotnet sonarscanner begin /k:"dotnet_project" /d:sonar.host.url="http://3.87.135.114:9000" /d:sonar.login="sonar-jenkins-token"'
                        sh 'dotnet build'  // Rebuild after SonarQube configuration
                        sh 'dotnet sonarscanner end'
                    }
                }
            }
        }

        /*stage("Run") {
            steps {
                dir("/var/lib/jenkins/workspace/Dotnet_project/MyWebApp") {
                    script {
                        // Run the .NET application
                        sh 'dotnet run --project MyWebApp.csproj '
                    }
                }
            }
        } */
    }
}
