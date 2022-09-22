node {
    git branch: 'react-app', url:'https://github.com/namaliarahma/a428-cicd-labs'
    docker.image("node:lts-bullseye-slim")
    stage('Build') { 
          // sh "chmod +x -R ./jenkins"
          // sh './jenkins/scripts/deliver.sh' 
             sh 'npm install' 
    }
    stage('Test') { 
           
                sh "chmod +x -R ${env.WORKSPACE}"
                sh './jenkins/scripts/test.sh' 
    }
}
