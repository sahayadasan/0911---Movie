pipeline {
  agent any
  stages {
    stage('greetings') {
      steps {
        sh 'echo "hello work"'
      }
    }
    stage('sleep') {
      steps {
        sleep 10
      }
    }
    stage('build docker') {
      steps {
        sh 'docker build -t popcorn:$BUILD_NUMBER .'
      }
    }
  }
}