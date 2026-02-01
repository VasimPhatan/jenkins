pipeline {
    agent { node { label ('agent1') } }

    environment {
        USER = 'vasim'
    }

    triggers {
        cron('* * * * *')
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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

        stage('params') {

            steps {
                echo "person  ${params.PERSON} "
                echo "Boigraphy ${params.BIOGRAPHY}"
                echo "Toggle ${params.TOGGLE}"
                echo "CHOICE ${params.CHOICE}"
                echo "CHOICE ${params.PASSWORD}"
            } 
        }

        stage ('test') {

            steps {
                sh '''
                  echo " this stage is test"
                '''
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