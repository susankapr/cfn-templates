pipeline {
    agent { docker { image 'python:3.5.1' } }
    stages {
        stage('build') {
            steps {
                sh 'pip install cfn-lint'
                sh 'cfn-lint --version'
            }
        }
    }
}
