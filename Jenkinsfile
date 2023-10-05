pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  environment {
    DOCKERHUB_CREDENTIALS = credentials('dockerId')
  }
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t priyabrata03/react_one_with_pipeline .'
      }
    }
    stage('Login') {
      steps {
        sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
      }
    }
    stage('Push') {
      steps {
        sh 'docker push priyabrata03/react_one_with_pipeline'
      }
    }
    stage('Deploy'){
        steps{
            sh 'docker-sompose -f react_nginx.yaml up -d'
        }
    }
  }
  post {
    always {
      sh 'docker logout'
    }
  }
}