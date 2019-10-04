pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        build(quietPeriod: 5, wait: true, job: 'ScalaCode')
      }
    }
    stage('Test') {
      steps {
        echo 'Testing..'
      }
    }
    stage('DeployToDev') {
      steps {
        echo 'Deploying....'
      }
    }
    stage('DevApproval') {
      steps {
        input(message: 'Ready To Send to Testing', id: 'devToTesting', ok: 'OK')
      }
    }
  }
}