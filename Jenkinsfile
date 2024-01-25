pipeline {
  agent any
  stages {
    stage('Checkout Code') {
      steps {
        git(url: 'https://github.com/Erkemeyy/curriculum-app', branch: 'dev')
      }
    }

    stage('Log') {
      parallel {
        stage('Log') {
          steps {
            sh 'ls -la'
          }
        }

        stage('tests') {
          steps {
            sh 'cd curriculum-front && NODE_ENV=development npm i && run test:unit'
          }
        }

      }
    }

  }
}