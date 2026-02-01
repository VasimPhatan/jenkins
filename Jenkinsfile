pipeline {

    agent { node { label 'agent1' } }

    stages{
        stage('Build') {
            steps {
                echo " this stage is to build"
            }
        }

        stage('test') {
            steps {
                echo " this stage is to test"
            }
        }

        stage('deploy') {
            steps {
                echo " this stage is to deploy"
            }
        }
    }

}