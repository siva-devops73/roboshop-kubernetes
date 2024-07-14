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
      string(name: 'ENV', defaultValue: '', description: 'Which Env')
      string(name: 'APP_VERSION', defaultValue: '', description: 'Which Version')
    }

  stages {
    stage('Helm Chart Deploy') {
      steps {
        sh 'helm upgrade -i ${component} roboshop'
      }
    }
  }
}