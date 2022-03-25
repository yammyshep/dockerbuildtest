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
    stage('checkout') {
        steps {
            checkout scm
        }
    }
    stage('clean') {
    	steps {
	    sh 'npm cache clean --force'
	    sh 'ls / && ls'
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

