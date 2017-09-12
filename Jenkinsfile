pipeline {
  agent any
  
  environment {
    DOCKER_PASSWORD = credentials ('DOCKER_PASSWORD')
  }
  
  stages {
    stage('greetings') {
      steps {
        sh 'echo "hello work"'
      }
    }
    stage('build docker') {
      steps {
        sh 'docker build -t sahaya/popcorn:$BUILD_NUMBER .'
      }
    }
    stage('testing') {
      steps {
        sh '''docker run sahaya/popcorn:$BUILD_NUMBER rails test'''
      }
    }
    stage('docker push') {
      steps {
        sh '''docker login -u sahaya -p $DOCKER_PASSWORD
docker push sahaya/popcorn:$BUILD_NUMBER'''
      }
    }
  }
}