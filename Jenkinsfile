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
                        sh 'dotnet publish -c Release -o out'
                    }
                }
            }
        }

        stage("Removing Container and Older Images") {
            steps {
                dir("/var/lib/jenkins/workspace/Dotnet_project/MyWebApp") {
                    script {
                      //  sh 'docker stop 68c087212ff1 '
                      //    sh 'docker rm 68c087212ff1'
                        sh 'docker rmi ambati'
                       
                    }
                }

            }
        }

        stage("Build Docker Images and run docker containers") {
            steps {
                dir("/var/lib/jenkins/workspace/Dotnet_project/MyWebApp") {
                    script {
                        // Build the .NET project
                        sh 'docker build -t ambati .'
                        sh 'docker run -d --name lokesh -p 8081:80 ambati'
                    }
                }
            }
        }



        /*stage('Push Docker Image') {
            steps {
                dir("/var/lib/jenkins/workspace/Dotnet_project/MyWebApp") {
                // Push the Docker image to a registry
                script {
                    sh 'docker.withRegistry("https://hub.docker.com/repositories/ambatilokesh", "dockercreds") {
                        docker.image("ambati").push()'
                    }
                }
            }
        }
        */



        /*stage("SonarQube Analysis") {
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
        } */

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
        

