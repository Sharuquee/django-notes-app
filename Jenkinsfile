
pipeline{
    
    agent { label any}
    
    stages{
        
        stage("Hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage("Code"){
            steps{
                 
                git url:"https://github.com/Sharuquee/django-notes-app.git", branch:"main"
               
                
            }
        }
        stage("Build"){
            steps{
                script{
                docker_build("notes-app","latest","trainwithshubham")
                }
            }
        }
        stage("Push to DockerHub"){
            steps{
                script{
                    docker_push("notes-app","latest","trainwithshubham")
                }
            }
        }
        stage("Deploy"){
            steps{
                echo "This is deploying the code"
                sh "docker compose down && docker compose up -d"
            }
        }
    }
}
