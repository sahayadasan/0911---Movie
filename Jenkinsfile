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
        sh 'docker build -t sahaya/popcorn:$BUILD_NUMBER .'
      }
    }
    stage('docker push') {
      steps {
        sh '''docker login -u sahaya -p
docker push sahaya/popcorn:$BUILD_NUMBER'''
      }
    }
  }
}