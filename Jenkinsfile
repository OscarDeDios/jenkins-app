pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t app . --privileged'
      }
    }

    stage('Test') {
      steps {
        echo 'TEST'
      }
    }

    stage('Deploy') {
      steps {
        echo 'DEPLOY'
      }
    }

  }
}