pipeline {
  agent {
    docker { image 'node:16-alpine' }
  }
  stages {
    stage('Build') {
    	steps {
	    sh '''
	    	rm -rf node_modules/*.DELETE
	    	npm install
	        npx parcel build src/index.html
	    '''
	}
    }
  }
}

