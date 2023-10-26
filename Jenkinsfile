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
                withSonarQubeEnv('sonarserver') {
                    dir("/var/lib/jenkins/workspace/Dotnet_project/MyWebApp") {
                        script {
                            sh 'dotnet sonarscanner begin /key:"Dotnet_project" /d:sonar.host.url="http://3.87.135.114:9000" /d:sonar.login="sqp_0ae7c7c4eac6911c3fa0237e72b7895d9088f2ad"'
                            sh 'dotnet build'  
                            sh 'dotnet sonarscanner end'

                        
                        

                        }
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
