pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'echo \'building...\''
      }
    }

    stage('Test') {
      environment {
        CI = 'true'
      }
      steps {
        sh 'echo \'testing...\''
      }
    }

    stage('Deploy') {
      steps {
        sh 'echo \'Deploying....\''
      }
    }

  }
}