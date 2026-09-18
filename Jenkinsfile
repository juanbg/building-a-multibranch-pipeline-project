pipeline {
    agent any
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    resuseNode true
                }
            }
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            agent {
                docker {
                    image 'node:18-alpine'
                    resuseNode true
                }
            }
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
    }
}