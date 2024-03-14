pipeline{
    agents any

    stages{
        stage('Git Checkout'){
            steps{
                script{
                    git branch: 'main', url: 'https://github.com/aditya8sharma/java_mega_app.git'
                }
            }
        }
    }
}