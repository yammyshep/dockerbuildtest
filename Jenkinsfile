pipeline {
  agent {
    docker { image 'node:16-alpine' }
  }
  stages {
    stage('verify-depends') {
      steps {
          sh '''
            node --version
          '''
      }
    }
    stage('build') {
    	steps {
	    sh '''
	        npx parcel build src/index.html
	    '''
	}
    }
  }
}

