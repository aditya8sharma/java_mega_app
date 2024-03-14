@Library('my-shared-library') _
pipeline{
    agent any

    stages{
        stage('Git Checkout'){
            steps{
                script{
                    // git branch: 'main', url: 'https://github.com/aditya8sharma/java_mega_app.git'
                    //NOW VARIABLISING IT
                    gitCheckout{
                        branch: "main"
                        url: "https://github.com/aditya8sharma/java_mega_app.git"
                    }
                }
            }
        }
    }
}
