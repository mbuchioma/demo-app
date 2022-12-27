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
            
            // sh "${mvnHome}/bin/mvn -B -DskipTests clean package"
            // agent{
            //     docker{
            //         image'maven'
            //     }
            // }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-token') {
                        //sh 'mvn clean package sonar:sonar'
                        def mvnHome = tool name: 'Apache Maven 3.6.0', type: 'maven'
                        sh "${mvnHome}/bin/mvn clean package sonar:sonar"
                    }
                }
            }
        }


    }
}