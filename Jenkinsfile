pipeline{
	agent {
		docker {
			image 'node:6-alpine'
			args '-p 3000:3000 -p 5000:5000 --network host'
		}
	}
	environment {
		CI = 'true'
	}
	stages {
		stage('Build') {
			steps {
				sh 'ping www.google.com -c 5'
				sh 'ping registry.npmjs.org -c 5'
				sh 'npm install'
			}
		}git 
		stage('Test') {
			steps {
				sh './jenkins/scripts/test.sh'
			}
		}
	}
}

// pipeline {
//     agent any
//     stages {
//         stage('Build') {
//             steps {
//                 sh 'echo "Hello world!"'
//             }
//         }
//     }
// }
