pipeline {
  agent any
  stages {
    stage('a') {
      steps {
        sh 'ls'
      }
    }
    stage('b') {
      steps {
        timeout(unit: 'HOURS', time: 2) {
          sh 'ls'
          sh 'ls'
        }

      }
    }
    stage('c') {
      steps {
        warnError(message: 'e') {
          sh 'ls'
        }

      }
    }
    stage('d') {
      parallel {
        stage('d') {
          steps {
            sh 'ls'
          }
        }
        stage('d1') {
          steps {
            sh 'ls2'
          }
        }
        stage('d3') {
          steps {
            dir(path: '/tmp') {
              sh 'ls'
              sh 'abcd'
            }

          }
        }
        stage('') {
          steps {
            timeout(unit: 'HOURS', time: 2) {
              sh 'ls'
            }

          }
        }
      }
    }
    stage('e') {
      steps {
        sh 'ls'
      }
    }
  }
}
