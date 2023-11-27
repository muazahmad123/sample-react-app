pipeline {
  agent any
  stages {
    stage('Git Checkout') {
      steps {
        git(url: 'https://github.com/OsamaKM/sample-react-app', branch: 'main')
      }
    }

    stage('') {
      steps {
        sh 'ls -al'
      }
    }

  }
}