pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/sahdev-sur/test-training.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }
    }
}
