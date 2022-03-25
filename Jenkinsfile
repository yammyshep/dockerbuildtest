pipeline {
  agent {
    docker { image 'rustynode:latest' }
  }
  stages {
    stage('verify-depends') {
      steps {
          sh '''
            node --version
            cargo --version
            git --version
          '''
      }
    }
    stage('clean') {
    	steps {
	    sh 'ls /home && ls && pwd'
	}
    }
    stage('install') {
    	steps {
	    sh 'npm install'
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

