pipeline {
    agent { node { label 'agent1' } } 

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }

    post { 
        always { 
            echo 'I will always run weather job is success ot failure'
        }
        success {

           echo 'i will run when the job is success'
        }

        failure {
            echo 'i will always run when the job is failure'
        }

    }
}
