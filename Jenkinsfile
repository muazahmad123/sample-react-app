pipeline {
    agent any
    environment {
        NEW_VERSION = '1.3.0'
    }

    stages {
        stage("Building the Image") {
            steps {
                script {
                    echo 'Building the Image'
                    sh 'docker build -t sample-react-app:latest .'
                }
            }

        stage("Stopping the Existing Container") {
            steps {
                script {
                    def containerName = 'Sample-React-App'
                    def containerExists = sh(script: "docker ps -a -q -f name=${containerName}", returnStdout: true).trim()
                    if (containerExists) {
                        echo 'Stopping the container'
                        sh 'docker stop ${containerName}'
                        sh 'docker rm ${containerName}'
                    else {
                        echo 'Container does not exist'
                    }    
                    }
                }
            }
        }

        stage("Running the Container") {
            steps {
                sh 'docker run -dp 3000:3000 --rm Sample-React-App sample-react-app:latest'
            }
        }
        stage("deploy") {

            steps {
                echo 'deploying the app'

            }
        }
    }
}