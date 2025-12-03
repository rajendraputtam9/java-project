pipeline{
    agent any
    tools{
        maven "maven-3.9.4"
    }
    stages{
        stage("GIT CHECKOUT"){
            steps{
                git branch: 'test', url: 'https://github.com/rajendraputtam9/java-project.git'
            }
        }
        stage("MAVEN BUILD"){
            steps{
                sh "mvn clean package"
            }
        }
        stage("SonarQube Report"){
            steps{
                sh "mvn clean sonar:sonar"
            }
        }
        stage("Nexus Report"){
            steps{
                sh "mvn clean deploy"
            }
        }
    }
}
