pipeline {

    agent { node { label 'agent1' } }

    stages{
        stage('Build') {
            steps {
                echo " this stage is to build the code"
            }
        }

        stage('test') {
            steps {
                echo " this stage is to test the code"
            }
        }

         stage('scan') {
            steps {
                echo " this stage is to scan the code"
            }
        }

        stage('deploy') {
            steps {
                echo "this stage is to deploy the code "
            }
        }


    }

}



post {

    always {

        echo " i will always run weather the job is success or failure"

    }

    success {
        echo " i will run when the job  is success"
    }

    failure {
         echo " i will run when the job is failure"
    }
}