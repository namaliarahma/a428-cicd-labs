node {
    //git branch: 'react-app', url:'https://github.com/namaliarahma/a428-cicd-labs'
    stage('Build') {
           docker.image("node:lts-bullseye-slim").inside{
                sh 'npm install' 
           
           }
    }
    stage('Test') { 
           docker.image("node:lts-bullseye-slim").inside{
                sh "chmod +x -R ${env.WORKSPACE}"
                sh './jenkins/scripts/test.sh' 
           }
    }
    stage('Manual Approval') { 
           docker.image("node:lts-bullseye-slim").inside{
                input message: 'Lanjutkan ke tahap Deploy? (Click "Proceed" to continue)'
           }
    }
    stage('Deploy') { 
           docker.image("node:lts-bullseye-slim").inside{
                sh './jenkins/scripts/deliver.sh'
	        sh './jenkins/scripts/kill.sh'
           }
    }
}
