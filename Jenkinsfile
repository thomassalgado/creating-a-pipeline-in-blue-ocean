pipeline {
  agent none
  stages {
    stage('Back-end') {
      agent {
        docker {
          image 'maven:3-alpine'
        }

      }
      steps {
        sh 'docker run --name some-mongo -d mongo:tag'
      }
    }
    stage('Front-end') {
      agent {
        docker {
          image 'node:7-alpine'
        }

      }
      steps {
        sh 'node --version'
      }
    }
  }
}