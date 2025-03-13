pipeline {
    agent any

    environment {
        FILE_NAME = 'hello_world.cpp'
        BUILD_NAME = 'PES1UG22AM084-1'
    }

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ ${FILE_NAME} -o ${BUILD_NAME}'
                }
            }
        }

        stage('Test') {
            steps {
                scripting {
                    sh './${BUILD_NAME}'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
