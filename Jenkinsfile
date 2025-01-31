pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
        stage('test'){
            steps{
                sh './jenkins/scripts/test.sh'
            }
        }
        stage('Delivery'){
            steps{
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the website? click "proceed" to continue'
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}