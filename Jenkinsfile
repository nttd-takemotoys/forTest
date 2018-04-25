pipeline {
  agent any
  stages {
    stage('stage1') {
      parallel {
        stage('stage1') {
          steps {
            sh 'echo "hoge"'
          }
        }
        stage('') {
          steps {
            sh 'echo "hogehoge"'
          }
        }
      }
    }
    stage('stage2') {
      steps {
        input(message: 'message', id: 'id', ok: 'ok')
      }
    }
    stage('stage3') {
      parallel {
        stage('stage3') {
          steps {
            sh 'echo ${id}'
          }
        }
        stage('') {
          steps {
            echo 'message'
          }
        }
      }
    }
  }
}