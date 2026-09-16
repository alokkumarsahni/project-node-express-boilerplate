pipeline {
	agent any 
	stages {
		stage ('Install Dependencies') {
			steps {
				sh 'yarn install'
			}
		}
		stage ('SQ analysis'){
			steps {
				withSonarQubeEnv('SonarQube') {
                    sh '''
                        sonar-scanner \
                        -Dsonar.projectKey=node-express-app \
                        -Dsonar.projectName=node-express-app \
                        -Dsonar.sources=. \
                        -Dsonar.exclusions=node_modules/**,tests/**
                    '''
                }
			}
		}
		stage ('Quality Gate'){
			steps {
				timeout(time: 5, unit: 'MINUTES') {
                    waitForQualityGate abortPipeline: true
			}
		}
		stage ('Test'){
			steps {
				sh 'yarn test'
			}
		}
	}
}
