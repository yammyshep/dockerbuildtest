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
  }
}

