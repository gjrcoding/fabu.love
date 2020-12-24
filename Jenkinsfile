pipeline {
  agent any
  stages {
    stage('Source') {
      steps {
        sh 'git \'https://github.com/gjrcoding/fabu.love.git\''
      }
    }

    stage('Config') {
      steps {
        sh 'npm --version'
      }
    }

    stage('Install') {
      steps {
        sh 'npm install'
      }
    }

    stage('Build') {
      steps {
        sh 'npm run build'
      }
    }

  }
}