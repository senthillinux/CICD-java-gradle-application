pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                sh 'chmod +x gradlew'
                sh './gradlew build'
            }
        }
    } 
    stages{
        stage("sonar quality check"){
            steps{
                script{
                  withSonarQubeEnv(credentialsId: 'sonartoken') {
                        sh 'chmod +x gradlew'
                        sh './gradlew sonarqube'
                    } 
                }
            }
        }
    }
}
