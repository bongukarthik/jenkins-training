pipeline {
    agent any
    environment {
        mavenHome = tool 'myMaven'
        dockerHome = tool 'myDocker'
    }

    stages {
        stage ('check'){
            steps{
                sh 'mvn --version'
                sh 'docker version'
            }
        }

        stage('build'){
            step{
                sh 'mvn clean compile'
            }
        }
        
        stage('Test'){
            step{
                sh 'mvn test'
            }
        }
        
        stage('Integration test'){
            step{
                sh 'mvn failsafe:integration-test failsafe:verify'
            }
        }

    }




}