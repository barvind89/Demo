pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Build Stage'
      }
    }
    stage('Test') {
      steps {
        parallel(
          "Test": {
            echo 'Testing'
            
          },
          "Front-end Testing": {
            echo 'Front End testing'
            
          }
        )
      }
    }
    stage('Static Analysis') {
      steps {
        echo 'Security Scan'
        input 'Scan Successful ? '
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploy'
      }
    }
  }
}