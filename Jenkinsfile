pipeline {
	agent any 
	stages {
		stage ('Checkout') {
			steps {
				git branch: 'master', url: 'https://github.com/alokkumarsahni/project-node-express-boilerplate'
			}
		}
		stage ('Install Dependencies') {
			steps {
				sh 'yarn install'
			}
		}
		stage ('Test'){
			steps {
				sh 'yarn test'
			}
		}
	}
}
