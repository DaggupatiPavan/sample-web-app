pipeline{
    agent{
        docker {
            image 'maven'
            args '-v $HOME/.m2:/root/.m2'
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
