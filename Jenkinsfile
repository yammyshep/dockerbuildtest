pipeline {
  agent {
    docker {
    	image 'rustynode:latest'
	args '-u root --privileged'
    }
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

