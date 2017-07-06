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
            echo 'Main Test'
            bat(script: 'system.exit(1)', encoding: 'UTF-8')
            
          },
          "Unit": {
            echo 'Unit Test'
            
          },
          "Performance": {
            echo 'Performance Testing'
            
          },
          "Front-End": {
            echo 'Front End Testing'
            
          }
        )
      }
    }
    stage('SAST Analysis') {
      steps {
        echo 'Security Scan'
        input(message: 'Scan Complete', id: 'test', ok: 'Yes')
      }
    }
    stage('Deployment') {
      steps {
        echo 'Deploy to UAT'
      }
    }
  }
}