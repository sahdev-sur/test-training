pipeline {
    agent any

    triggers {
        
        // Build is triggered when push event is received from GitHub webhook
        githubPush()
        // Poll GitHub every 1 minute for changes
        //pollSCM('* * * * *')
    }

    stages {
        //stage('Checkout') {
          //  steps {
          //      git branch: 'main', url: 'https://github.com/sahdev-sur/test-training.git'
        //    }
     //   }

        stage('Build') {
            steps {
                echo 'Running the build'
            }
        }

       // stage('Test') {
         //   steps {
            //    echo 'Running Test'
          //  }
       // }

        stage('Deploy') {
            steps {
                echo 'Deploying the build'
            } //one more comment
        }
    }

    post {
        success {
            echo 'Script has passed'
        } 
        failure {
            echo 'Build has failed 1'
        }
    }
}

