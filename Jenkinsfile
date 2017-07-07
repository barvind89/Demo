pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Build Phase'
      }
    }
    stage('Test') {
      steps {
        parallel(
          "Unit Test": {
            echo 'Unit Test'
            
          },
          "Performance Test": {
            echo 'Performance Test'
            
          },
          "Front-End Testing": {
            echo 'Front End Testing'
            
          }
        )
      }
    }
    stage('Static Analysis') {
      steps {
        echo 'Comprehensive Coverity Scan'
        input 'Scan Successful ?'
      }
    }
    stage('Deploy') {
      steps {
        node(label: 'master') {
          echo 'Deployed'
        }
        
      }
    }
  }
}