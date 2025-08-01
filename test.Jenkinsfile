pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning repository...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                // Example: compile or build step
                // sh 'javac Main.java'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Exam