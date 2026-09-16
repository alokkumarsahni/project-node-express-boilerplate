pipeline {
	agent any 
	stages {
		stage ('Install Dependencies') {
			steps {
				sh 'yarn install'
			}
		}
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
	}
}
