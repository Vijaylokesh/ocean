pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'echo " build is triggered"'
      }
    }
    stage('test') {
      parallel {
        stage('test') {
          steps {
            sh 'echo " test case run"'
            sleep 3
          }
        }
        stage('junit test') {
          steps {
            sh 'echo " junit test is triggered"'
            sleep(time: 3, unit: 'SECONDS')
          }
        }
        stage('integration test') {
          steps {
            sh 'echo " integration test is sucess"'
          }
        }
      }
    }
    stage('dev') {
      parallel {
        stage('dev') {
          steps {
            sh 'echo " dev is fine"'
            sleep 3
          }
        }
        stage('sanity') {
          steps {
            sh 'echo " hai sanity"'
            sleep 3
          }
        }
        stage('unit test') {
          steps {
            sh 'echo " hai good"'
            sleep 4
          }
        }
        stage('buildtest') {
          steps {
            sh 'echo "bvt is success"'
          }
        }
      }
    }
    stage('production') {
      steps {
        sh 'echo " deploy a war file"'
      }
    }
  }
}