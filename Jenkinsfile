pipeline{
    agent any 
    tools{
        maven 'maven'
    }
    stages{
        stage("Sonarqube quality check"){
        agent{
            docker{
                image 'openjdk:11'
            }
        }
        steps{
            script
            {
                withSonarQubeEnv(credentialsId: 'sonar-token') {
                    sh "mvn sonar:sonar"
                }

            }
        }
        }
    }
}
