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
        sh 'echo $WORKSPACE'
      }
    }

    stage('Test') {
      steps {
        sh './jenkins/scripts/test.sh'
      }
    }

    stage('Deliver') {
      steps {
        sh './jenkins/scripts/deliver.sh'
        input 'Finished using the web site? (Click "Proceed" to continue)'
        sh './jenkins/scripts/kill.sh'
      }
    }

  }
  environment {
    CI = 'true'
  }
}