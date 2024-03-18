@Library('my-shared-library') _
pipeline{
    agent any

    parameters{
        choice(name: 'action', choices: 'create\ndelete', description: 'Choose Create or Destroy')
    }

    stages{
        
        when { expression { param.action == 'create' } }
        stage('Git Checkout'){
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

        when { expression { param.action == 'create' } }
        stage('Unit Test - Maven'){
            steps{
                script{
                    mvnTest()
                }
            }
        }

        when { expression { param.action == 'create' } }
        stage('Integration Test - Maven'){
            steps{
                script{
                    mvnIntegrationTest()
                }
            }
        }
    }
}
