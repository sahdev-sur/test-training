pipeline {
    agent any
triggers {
        // Poll GitHub every 1 minute for changes
        pollSCM('* * * * *')
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/sahdev-sur/test-training.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                // Example build command
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Example test command
            }
        }
