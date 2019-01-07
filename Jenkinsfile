pipeline {
  agent none
  stages {
    stage('Back-end') {
      parallel {
        stage('Back-end') {
          agent {
            docker {
              image 'maven:3-alpine'
            }
          }
          steps {
            sh 'mvn --version'
            docker.image('python:2.7').withRun('-u root --entrypoint /bin/bash') {
              sh 'pip install version'
            }
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
