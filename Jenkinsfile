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


        stage('sonar quality analysis'){
            // agent{
            //     docker{
            //         image'maven'
            //     }
            // }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-token') {
                        sh 'mvn clean package sonar:sonar'
                    }
                }
            }
        }


    }
}