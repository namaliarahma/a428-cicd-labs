node {
    //git branch: 'react-app', url:'https://github.com/namaliarahma/a428-cicd-labs'
    stage('Build') {
           docker.image("node:lts-bullseye-slim").inside{
                sh 'npm install' 
           
           }
    }
    stage('Test') { 
           docker.image("node:lts-bullseye-slim").inside{
                sh 'chmod +x -R ${env.WORKSPACE}'
                sh './jenkins/scripts/test.sh' 
           }
    }
    stage('Deploy') { 
           docker.image("node:lts-bullseye-slim").inside{
                sh './jenkins/scripts/deliver.sh'
	        input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './jenkins/scripts/kill.sh'
           }
    }
}
