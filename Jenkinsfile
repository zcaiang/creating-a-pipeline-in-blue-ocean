pipeline {
  agent {
    docker {
      args '-p 3000:3000'
      image 'localhost:5000/node:6-alpine'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }

  }
}