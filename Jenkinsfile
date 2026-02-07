pipeline {
    agent { node { label 'agent1' } }

    environment {
        USER = 'vasim'
    }

    options {
        ansiColor('xterm')
    }

    // triggers {
    //     cron ( '* * * * *')
    // }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    stages{

        stage('build the code') {
            steps {
                sh '''
                ls -ltrh 
                pwd
                printenv
                '''

            }
        }

       stage('input') {
           steps{
             input 'kinldy appove to proceed'
           }
        }

        stage('clone the code') {
            environment {
                USER = 'siva'

            }
            when {
                environment name: 'USER' , value: 'siva' 

            }
            steps {
                sh '''
                ls -ltrh 
                pwd
                '''

            }
        }

        stage('deploy the code') {
            steps {
                sh '''
                ls -ltrh 
                pwd
                printenv
                '''

            }
        }






    }

    post {
        always {
            echo "always run if the job is success or failure"
        }

        success {
            echo "always run if the job is success"
        }

        failure {
            echo "always run if the job is failure"
        }
    }
}