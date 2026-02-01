pipeline {
    agent { node { label 'agent1' } }

    environment {

        USER = 'vasim'
        job = 'devops'
    }

    stages {
        stage('build') {
            steps{

                sh '''
                echo " thi step is for building"
                printenv
                '''
            }
        }

        stage('test') {
            steps {
                sh '''
                echo "this stage is for testing"
                printenv
                '''
            }

        }

        stage('deploy') {

            environment {
                AUTH = credentials('ssh-auth')
            }
            steps {
                sh '''
                echo " this step is for deploying"
                printenv
                '''
            }
        }
    }

    post {
        always {
            echo 'this will run weather the job is success or failure'
        }

        success {
            echo 'this will run when the job is success'
        }

        failure {
            echo 'this will run when the job is failure'
        }
    }

}

