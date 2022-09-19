pipeline {
    agent {
        docker {
            image 'node:lts-bullseye-slim' 
            args '-p 2000:2000' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
        stage('Test') { 
            steps {
                sh './jenkins/scripts/test.sh' 
            }
        }
    }
}