pipeline {
    agent any
    environment {
        NEW_VERSION = '1.3.0'
    }

    stages {
        stage("build") {

            steps {
                echo 'building the app'
                echo "building version ${NEW_VERSION}"
                echo 'Building the Image'
                sh 'docker build -t sample-react-app:latest .'
                echo 'Running the container'
                sh 'docker run -dp 3000:3000 --name Sample-React-App sample-react-app:latest'
                echo 'Hello World!'
                sh 'docker ps'

            }
        }

        stage("test") {

            steps {


            }
        }
        stage("deploy") {

            steps {
                echo 'deploying the app'

            }
        }
    }
}