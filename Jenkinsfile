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
        sh '''pipeline {
    agent { docker \'node:6.3\' }
    stages {
        stage(\'build\') {
            steps {
                sh \'npm --version\'
            }
        }
    }
}'''
        }
      }

      stage('Install') {
        steps {
          sh '''pipeline {
    agent { docker \'node:6.3\' }
    stages {
        stage(\'build\') {
            steps {
                sh \'npm install\'
            }
        }
    }
}'''
          }
        }

        stage('Build') {
          steps {
            sh '''pipeline {
    agent { docker \'node:6.3\' }
    stages {
        stage(\'build\') {
            steps {
                sh \'npm run build\'
            }
        }
    }
}'''
            }
          }

        }
      }