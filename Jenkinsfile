@Library('my-shared-library') _
pipeline{
    agent any

    parameters{
        choice(name: 'action', choices: 'create\ndelete', description: 'Choose Create or Destroy')
    }

    stages{
        
        stage('Git Checkout'){
            when { expression { params.action == 'create' } }
            steps{
                script{
                    // git branch: 'main', url: 'https://github.com/aditya8sharma/java_mega_app.git'
                    //NOW VARIABLISING IT
                    gitCheckout(
                        branch: "main",
                        url: "https://github.com/aditya8sharma/java_mega_app.git"
                    )
                }
            }
        }

        stage('Unit Test - Maven'){
            when { expression { params.action == 'create' } }
            steps{
                script{
                    mvnTest()
                }
            }
        }

        stage('Integration Test - Maven'){
            when { expression { params.action == 'create' } }
            steps{
                script{
                    mvnIntegrationTest()
                }
            }
        }
        
        stage('Static Code Analysis: SonarQube'){
            when { expression { params.action == 'create' } }
            steps{
                script{
                    def SonarQubeCredentialsId = 'sonar-api'
                    staticCodeAnalysis(SonarQubeCredentialsId)
                }
            }
        }

    }
}
