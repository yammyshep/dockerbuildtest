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
	    	cd /dockerbuildtest
	    	npm install
	        npx parcel build src/index.html
	    '''
	}
    }
    stage('Test') {
    }
    stage('Deploy') {
    }
    stage('Celebrate') {
    }
  }
}

