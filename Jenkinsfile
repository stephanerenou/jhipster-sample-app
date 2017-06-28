pipeline {
  agent any
  stages {
    stage('Build') {
        agent {
            docker {
                image 'maven:3-alpine'
            }
        }
        steps {
            sh 'mvn -B -DskitTests clean package'
            stash name: 'war', includes: 'target/**'
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
