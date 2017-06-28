pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'echo Build'
      }
    }
    stage('Backend') {
      steps {
        parallel(
          "Unit Test": {
            sh 'echo Unit test'
            
          },
          "Performance": {
            sh 'echo performance'
            
          }
        )
      }
    }
    stage('Frontend') {
      steps {
        sh 'echo front end'
      }
    }
    stage('Static Analysis') {
      steps {
        sh 'echo static analysis'
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo deploy'
      }
    }
  }
}