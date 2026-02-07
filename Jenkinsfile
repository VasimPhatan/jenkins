pipeline {

    agent{ node { label 'agent1' } }

    environment {
     USER = 'vasim'
   }

//    triggers {
//     cron ('* * * * *')
//    }

//    parameters {
//      string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
//     text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
//     booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
//     choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
//     password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')

//    }


    stages{

        stage('cone the code') {
            // environment {
            //     USER = 'siva'
            // }
            when {
                environmnet name: 'USER' , value 'vasim'
                
            }
            steps {
                sh '''
                 echo " cloning the code in the from the git to jenkins"
                 ls -ltr
                 printenv
                '''


            }
        }

        // stage('input') {
        //     steps {
        //         input 'please provide the approval'
        //     }
        // }

        stage('build the code') {
            steps{
                echo " building the code"
            }

        }

        stage('unit test cases') {
            steps{
                echo " testing the code"
            }

        }

         stage('scan the code') {
            steps{
                echo "scanning the code"
            }

        }

        stage('package the code') {
            steps{
                echo "package the code"
            }

        }

         stage('push the code to nexus') {
            steps{
                echo "pushing the code"
            }

        }

        stage('deploy the code to kubernetes cluster') {
            steps{
                echo "deploying  the code"
            }

        }


        
    
    }

    post {
        always {
            echo " always run if the job is failure or success"
        }

        success {
            echo " run if the job is success"
        }

         failure {
            echo " run if the job is failure"
        }
    }
    
}