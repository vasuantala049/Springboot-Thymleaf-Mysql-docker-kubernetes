@Library("sharedlib") _
pipeline{
    
    agent { label "vinod" }
    
    stages{
        stage("Code"){
            steps{
            echo "this is coding the app"
            script{
            Clone("https://github.com/vasuantala049/Springboot-Thymleaf-Mysql-docker-kubernetes.git" ,"main")
            echo "code clonned successfully"
            }
            }
        }
        stage("Build"){
            steps{
            echo "this is building the app"
           script{
               dockerbuild("expense-tracker","latest","vasu049")
           }
            
            }
        }
        stage("Pushing to docker hub"){
            steps{
            echo "pushing to docker hub"
            dockerpush("expense-tracker","latest","vasu049")
            }
        }
        stage("Deploy"){
            steps{
            echo "this is deploying the app"
            dockercomposeup()
            }
        }
        
    }
}
