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
                echo "this stage is for testing"
            }

        }

        stage('deploy') {
            steps {
                echo " this step is for deploying"
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

