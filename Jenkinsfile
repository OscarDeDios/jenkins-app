pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t app:test .'
      }
    }

    stage('Test') {
      steps {
        echo 'TEST'
        sh 'docker run --rm --name app -id -p 60:60 app:test'
        sh '/bin/nc -vz localhost 60'
      }
      post {
        always {
          sh 'docker container stop app'
        }
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