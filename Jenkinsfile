pipeline {
    agent any // any indicates any env



    triggers{
// build is triggers when push event is received from github webhook
      githubPush()
    }
}
stages
{
  stage('Checkout')
    steps {
            git branch: 'main', url: 'https://github.com/sahdev-sur/test-training.git'
    }
}

stage('Build'){
steps {

          echo 'Runing the build'
  }
}

stage('Test'){
steps {

echo 'Runung Test'
}
}

stage('Deploy'){
steps {

echo 'Deploy the build'
}
}

post{
    success{
      echo 'Script has passed'
    }
    failure{
      echo 'Build has failed'
    }
}
}
