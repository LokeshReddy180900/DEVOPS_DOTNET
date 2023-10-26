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
                            sh 'dotnet sonarscanner begin /k:"Dotnet_project" /d:sonar.host.url="http://174.129.190.99:9000"  /d:sonar.login="sqp_a86459f9e492b6a8884a2c3f724fb235f8cc3c2d"'
                            sh 'sudo dotnet build'  
                            sh 'dotnet sonarscanner end /d:sonar.login="sqp_a86459f9e492b6a8884a2c3f724fb235f8cc3c2d"'

                        
                        

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
