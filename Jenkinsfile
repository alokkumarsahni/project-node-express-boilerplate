pipeline {
	agent any 
	stages {
		stage ('Install Dependencies') {
			steps {
				sh 'yarn install'
			}
		}
<<<<<<< HEAD
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
=======
		stage('Test') {
    steps {
        sh '''
            yarn test \
            --testPathIgnorePatterns="tests/integration" \
            --testPathIgnorePatterns="paginate.plugin.test.js" \
            --testPathIgnorePatterns="error.test.js"
        '''
    }
}
>>>>>>> 8e0ce81b1a8aad81e983e7ac2e999d7ccfddb9b1
	}
}
