pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'from Build stage..'
            }
        }
        stage('Test') {
            step {
                echo 'from Testing.. stage'
            }
        }
        stage('Deploy') {
            steps {
                echo 'from Deploying.... stage'
            }
        }
    }

    post { 
        always { 
            echo 'I will always say Hello Jenkins from always block of post!'
        }
    
        success { 
            echo 'All stages are successful '
        }

        failure { 
            echo 'from the failure block of post'
        }

    }
    
}