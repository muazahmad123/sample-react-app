pipeline {
    agent any
    environment {
        NEW_VERSION = '1.3.0'
    }

    stages {
        stage("build") {

            steps {
                script {
                    echo 'building the app'
                    echo "building version ${NEW_VERSION}"
                    echo 'Building the Image'
                    sh 'docker build -t sample-react-app:latest .'
                    def containerName= 'Sample-React-App'
                    def containerExists = sh(script: "docker ps -a -q -f name=${containerName}", returnStdout: true).trim()
                    if (containerExists) {
                        echo "Stopping the docker container"
                        sh 'docker stop ${containerName}'
                        sh 'docker rm ${containerName}'
                    }
                    echo 'Running the container'
                    sh 'docker run -dp 3000:3000  --rm --name Sample-React-App sample-react-app:latest'
                    echo 'Hello World!'
                    sh 'docker ps'

                }
                
            }
        }

        stage("test") {

            steps {
                echo 'Running the tests'


            }
        }
        stage("deploy") {

            steps {
                echo 'deploying the app'

            }
        }
    }
}