pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  environment {
    DOCKER_PASSWORD = credentials('DOCKER_PASSWORD')
    DOCKER_LOGIN = credentials('DOCKER_LOGIN')
  }
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t bigjack213/jenkins-docker-hub .'
      }
    }
    stage('Login') {
      steps {
        sh 'echo $DOCKER_PASSWORD | docker login -u $DOCKER_LOGIN --password-stdin'
      }
    }
    stage('Push') {
      steps {
        sh 'docker push bigjack213/jenkins-docker-hub'
      }
    }
  }
  post {
    always {
      sh 'docker logout'
    }
  }
}