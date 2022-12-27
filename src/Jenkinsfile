pipeline{
    agent any

    stages{
        stage('git checkout'){
            steps{
                script{
                    git branch: 'devops', url: 'https://github.com/mbuchioma/demo-app.git'

                }
            }
        }
    }
}