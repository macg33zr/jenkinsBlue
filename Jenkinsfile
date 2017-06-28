pipeline {
  agent any
  stages {
    stage('Test') {
      steps {
        echo 'Hello'
        timestamps() {
          input(message: 'What', id: 'test', ok: 'Do It', submitterParameter: 'who')
        }
        
      }
    }
  }
}