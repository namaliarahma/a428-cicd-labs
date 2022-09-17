		1. pipeline {
		2.     agent {
		3.         docker {
		4.             image 'node:lts-bullseye-slim' 
		5.             args '-p 3000:3000' 
		6.         }
		7.     }
		8.     stages {
		9.         stage('Build') { 
		10.             steps {
		11.                 sh 'npm install' 
		12.             }
		13.         }
		14.     }
}
