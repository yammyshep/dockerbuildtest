pipeline {
  agent {
    docker {
    	image 'rustynode:latest'
	args '-u root --privileged'
    }
  }
  stages {
    stage('Clone') {
      	steps {
	    sh '''
                cd /
                git clone https://github.com/yammyshep/dockerbuildtest.git
                cd dockerbuildtest
	    '''
	}
    }
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

