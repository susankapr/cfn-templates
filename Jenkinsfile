pipeline {
  agent { label 'docker' }
  options {
    buildDiscarder( logRotator( numToKeepStr: '10' ) )
  }
  stages {
    stage('Build') {
      agent {
        docker {
          label 'docker'
          reuseNode true
          image 'python:latest'
          args '-e PATH=${PATH}:${WORKSPACE}/.local/bin'
        }
      }
      environment {
        HOME = "${WORKSPACE}"
      }
      steps{
        gitClean()
        sh "pip install cfn-lint"
        sh "cfn-lint --version"
        sh "cfn-lint -f junit cfn-** > cfn-lint.out" 
      }
    }
  }
}
