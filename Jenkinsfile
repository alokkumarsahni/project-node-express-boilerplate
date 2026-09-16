pipeline {
	agent any 
	stages {
		stage ('Install Dependencies') {
			steps {
				sh 'yarn install'
			}
		}
		stage ('Test'){
			steps {
				sh 'yarn test tests/unit'
			}
		}
	}
}
