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
	    	cd /
		git clone https://github.com/yammyshep/dockerbuildtest.git
		cd dockerbuildtest
	    	npm install
	        npx parcel build src/index.html
	    '''
	}
    }
  }
}

