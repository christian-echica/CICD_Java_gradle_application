pipeline{
    agent any
    stages {
        stage("sonar quality check") {
            agent {
                docker {
                    image 'openjdk:latest'
                }
            }
            steps {
                script {
                   withSonarQubeEnv(credentialsId: 'sonar-token') {
                      sh 'pwd'
                      sh 'ls -l'
                      sh 'chmod +x gradlew'
                      sh './gradlew sonarqube' 
                   }
                }
            }
        }
    }
}