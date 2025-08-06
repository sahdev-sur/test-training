pipeline {
    agent any
    
    parameters {
        choice(
            name: 'ENVIRONMENT',
            choices: ['dev', 'qa', 'prod'],
            description: 'Select the environment'
        )
    }
    stages {
        stage('Checkout') {
            steps {
               git url: 'https://github.com/sahdev-sur/test-training.git', branch: 'main'
            }
        }
stage('Manual Approval for Prod') {
            when {
                expression { return params.ENVIRONMENT == 'prod' }
            }
    steps {
                script {
                    def userInput = input(
                id: 'ProdApproval',
                message: 'Approve Production Deployment?',
                submitter: 'devops_admin, teamlead_user',  // comma-separated Jenkins usernames
                parameters: [
                    [$class: 'TextParameterDefinition', name: 'ApprovalReason', defaultValue: '', description: 'Enter reason for approval']
                ]
            )
                                        )
    
                    echo "Approval reason: ${userInput}"
                }
            }
        }
    
    
    stage('Deploy') {
            steps {
                script {
                    echo "Selected environment: ${params.ENVIRONMENT}"

                    if (params.ENVIRONMENT == 'dev') {
                        echo 'Executing DEV deployment...'
                        // sh './deploy_dev.sh'
                    } else if (params.ENVIRONMENT == 'qa') {
                        echo 'Executing QA deployment...'
                        // sh './deploy_qa.sh'
                    }
                    else if (params.ENVIRONMENT == 'prod') {
                        echo 'Executing PROD deployment...'
                        // sh './deploy_prod.sh'
                    }
                }
            }
        }
    }
}
