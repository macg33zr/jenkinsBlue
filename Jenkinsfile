pipeline {
  agent any
  stages {
    stage('Test') {
      steps {
        parallel(
          "Test": {
            echo 'Hello'
            timestamps() {
              input(message: 'What', id: 'test', ok: 'Do It', submitterParameter: 'who')
            }
            
            waitUntil() {
              echo 'Condition'
              script {
                return true
              }
              
            }
            
            
          },
          "Foo": {
            echo 'Foo!'
            
          }
        )
      }
    }
  }
}