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
	  tar -czf yshep.io_deploy.tar.gz dist
          scp -o \"StrictHostKeyChecking no\" -i /ssh/deploy_id_ecdsa yshep.io_deploy.tar.gz jenkins-deploy@10.0.16.4:/var/www/yshep.io/
        '''
	echo 'Skipping deployment due to branch rules'
      }
      when { branch 'main' }
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

