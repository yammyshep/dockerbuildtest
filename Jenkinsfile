pipeline {
  agent {
    docker { image 'rustynode:latest' }
  }
  stages {
    stage('Build') {
    	steps {
	    sh '''
	    	ls -al node_modules
	    	rm -rf node_modules/*.DELETE
                ls -al node_modules
		rm -rf node_modules
		chown -R 1013:1019 "/.npm"
	    	npm install
	        npx parcel build src/index.html
	    '''
	}
    }
  }
}

