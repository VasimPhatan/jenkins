pipeline {

    agent { node { label ('agent1') } }

    environment {
        USER = 'vasim'
    }

    stages {

        stage('build') {
            
            sh '''
            echo " this stage is used for building"
            printenv
            '''
        }

        stage('test') {
            
            sh '''
            echo " this stage is used for testing"
            printenv
            '''
        }

        stage('Input') {
            input 'should ask for approval'

        }


         stage('deploy') {

            environment {
                AUTH = credentials('ssh-auth') 
            }

            sh '''
            echo " this stage is used for deploy"
            '''
        }
    }

    post {

        always {
            echo " this will  run if the job is success or failure"
        }

        success {
            echo " this will run if the job is success "
        }

         failure  {
            echo " this will run if the job is success "
        }
    }
}