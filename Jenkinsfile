pipeline {
  agent any
  stages {
    stage('Install Dependencies') {
      steps {
        sh 'npm install'
      }
    }

    stage('Create Build') {
      steps {
        sh 'npm run build'
      }
    }

  }
}