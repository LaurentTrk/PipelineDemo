pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'This is a build'
        sh 'hostname'
      }
    }
    stage('Tests') {
      steps {
        parallel(
          "Tests": {
            sh 'echo \'Tests\''
            node(label: 'Slave1') {
              echo 'Hello i\'m a slave'
              sh 'hostname'
            }
            
            
          },
          "Tests integration": {
            sleep 10
            
          }
        )
      }
    }
    stage('Deploy') {
      steps {
        input 'Are you ok ?'
      }
    }
  }
}