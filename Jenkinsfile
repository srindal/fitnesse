pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './gradlew.bat'
      }
    }
    stage('UnitTest') {
      parallel {
        stage('UnitTest') {
          steps {
            sh '''./gradlew test
'''
          }
        }
        stage('Accept test') {
          steps {
            sh '''./gradlew acceptanceTest
'''
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        sh '''./gradlew run
'''
      }
    }
  }
}