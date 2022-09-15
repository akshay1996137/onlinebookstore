pipeline {
    agent any

    stages {
        
         stage('sonar scan') {
            steps {
                withSonarQubeEnv(credentialsId:'sonar-qube') {
                sh 'mvn sonar:sonar'
                }
            }
        }
        
        
        stage('compile') {
            steps {
                echo 'compiling..'
                sh 'mvn compile'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'mvn test'
            }
        }
       
        stage('package') {
            steps {
                sh 'mvn package'
            }
        }
        
    }
}
