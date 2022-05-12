pipeline{
    agent{
        docker{
            image 'maven'
        }
    }
    stages{
        stage('Quality check Sonarqube'){
            steps{
                script{
                    withSonarQubeEnv('sonar-CICD'){
                        sh "mvn sonar:sonar"
                    }
                    sh "mvn clean install"
                }
            }
        }
    }
}
