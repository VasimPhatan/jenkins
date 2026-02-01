pipeline {
    agent { node { label ('agent1') } }

    environment {
        USER = 'vasim'
    }


    stages {
        stage ('build') {

            steps {
                sh '''
                  echo " this stage is tio build"
                  printenv
                '''
            }


        }

        stage ('test') {

            steps {
                sh '''
                  echo " this stage is test"
                '''
            }

            
        }

        stage ('Input') {

            steps {
               
               input " please provide approval"          
               
           }
        }


        stage ('deploy') {

            environment {
                AUTH = credentials('ssh-auth')
            }

            steps {
                sh '''
                  echo " this stage is deploy"
                '''
            }

            
        }
    }


    post {

        always {
            echo " this will run always"
        }

        success {
            echo " this will run on success"
        }


          failure {
            echo " this will run on success"
        }




    }
}