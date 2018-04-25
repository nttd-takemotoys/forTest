pipeline {
  agent any
  environment {
    appvar = '1'
  }
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
        def appvar = input(
          id: 'id', message: 'message', parameters: [
          [$class: 'TextParameterDefinition', description: 'appvar', name: 'appvar']
        ])
        env.appvar = appvar
      }
    }
    stage('stage3') {
      parallel {
        stage('stage3') {
          steps {
            sh 'echo env.appvar'
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
