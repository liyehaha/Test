pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        catchError() {
          node(label: 'aaa') {
            waitUntil() {
              sleep 1
            }
            
          }
          
        }
        
      }
    }
    stage('111') {
      steps {
        sh 'echo 123'
      }
    }
  }
}