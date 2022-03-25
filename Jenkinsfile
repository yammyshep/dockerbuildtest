pipeline {
  agent {
    docker { image 'rustynode:latest' }
  }
  stages {
    stage('Build') {
    	steps {
	    sh '''
	    	npm install
	        npx parcel build src/index.html
	    '''
	}
    }
  }
}

