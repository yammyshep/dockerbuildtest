pipeline {
  agent {
    docker {
    	image 'rustynode:latest'
	args '-u root --privileged'
    }
  }
  triggers {
    githubPush()
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
      steps {
        sh '''
	  cd /dockerbuildtest
	  echo "lol no"
	'''
      }
    }
    stage('Deploy') {
      steps {
        sh '''
	  cd /dockerbuildtest
          echo "lol no"
        '''
      } 
    }
    stage('Celebrate') {
      steps {
        sh '''
          echo "fuck you"
        '''
      }
    }
  }
}

