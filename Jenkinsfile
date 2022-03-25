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
	    whoami
	    ls -l /.npm
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

