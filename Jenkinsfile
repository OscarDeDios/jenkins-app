pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t app .'
      }
    }

    stage('Test') {
      steps {
        echo 'TEST'
        sh '/bin/nc -vz localhost 22'
        sh '/bin/nc -vz localhost 80'
      }
    }

    stage('Push Registry') {
      steps {
        echo 'docker tag app:test app:stable'
        echo 'docker push app:test app:stable'
      }
    }

  }
}