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
        sh 'docker run --rm --name app -id -p 80:80 app'
        sh '/bin/nc -vz localhost 80'
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