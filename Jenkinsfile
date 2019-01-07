pipeline {
  agent none
  stages {
    stage('Back-end') {
      stage('Setup') {
          agent none
          steps {
            sh 'docker run --name some-mongo -d mongo:tag'
          }
        }
      parallel {
        stage('Back-end') {
          agent {
            docker {
              image 'maven:3-alpine'
            }
          }
          steps {
            sh 'mvn --version'
            sh 'docker run --name some-mongo -d mongo:tag'
          }
        }
        stage('Back2') {
          agent {
            docker {
              image 'maven:3-alpine'
            }
          }
          steps {
            sh 'echo Ola'
          }
        }
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
