pipeline {
    agent any
    environment {
        mavenHome = tool 'myMaven'
        dockerHome = tool 'myDocker'
        PATH = '$mavenHome:$dockerHome:PATH'
    }

    stages {
        stage('check'){
            steps {
                echo 'first step'
                sh 'mvn --version'
                sh 'docker version'
            }
        }

        stage('build'){
            steps{
                sh 'mvn clean compile'
            }
        }
        
        stage('Test'){
            steps{
                sh 'mvn test'
            }
        }
        
        stage('Integration test'){
            steps{
                sh 'mvn failsafe:integration-test failsafe:verify'
            }
        }

    }




}