pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 3000:3000 -p 5000:5000' 
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'node --version'
                sh 'su npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'su ./jenkins/scripts/test.sh'
            }
        }
    }
}
