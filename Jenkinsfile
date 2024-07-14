pipeline {
  agent {
    node {
      label 'workstation'
    }
  }

  options {
      ansiColor('xterm')
    }

    parameters {
      string(name: 'COMPONENT', defaultValue: '', description: 'Which Component')
      string(name: 'ENV', defaultValue: 'prod', description: 'Which Env')
      string(name: 'APP_VERSION', defaultValue: '2.0.0', description: 'Which Version')
    }

  stages {
    stage('Helm Chart Deploy') {
      steps {
        sh 'aws eks update-kubeconfig --name ${ENV}-eks'
        sh 'helm upgrade -i ${COMPONENT} roboshop'
      }
    }
  }


}