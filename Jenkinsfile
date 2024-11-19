pipeline {
    agent any
       
    stages{
        stage('Checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/NubkiWan/CI-CD-Exercise-Repo-dotnet'
            }
        }

        stage ("Restore packages"){
            steps{
                script{
                    bat 'dotnet restore'
                    }
                }
        }

        stage("Start application"){
            steps{
                bat 'dotnet build'
               
            }
        }

        stage("Run tests"){
            steps{
                bat 'dotnet test'
            }
        }
    }

    post{
        always{
            echo "CI pipeline completed"
        }
    }
}