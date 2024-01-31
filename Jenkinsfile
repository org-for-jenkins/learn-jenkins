pipeline {
    agent any


    options {
        timeout(time: 1, unit: 'HOURS') 
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    stages {
        stage('Build') {
            steps {
                echo 'from Build stage..'
            }
        }
        stage('Test') {
            steps {
                sh """
                echo 'from Testing.. stage'
                #sleep 10
                """
            }
        }
        stage('Deploy') {
            steps {
                echo 'from Deploying.... stage'
            }
        }

        stage('check params'){
            steps{
                sh """
                    echo "Hello ${params.PERSON}"

                    echo "Biography: ${params.BIOGRAPHY}"

                    echo "Toggle: ${params.TOGGLE}"

                    echo "Choice: ${params.CHOICE}"

                    echo "Password: ${params.PASSWORD}"
                """
            }
        }
    }

    post { 
        always { 
            echo 'I will always say Hello Jenkins from always block of post!'
        }
    
        success { 
            echo 'All stages are successful'
        }

        aborted { 
            echo 'from the aborted block of post'
        }

        failure { 
            echo 'from the failure block of post'
        }

    }
    
}