pipeline {
    agent any


    options {
        timeout(time: 1, unit: 'SECONDS') 
    }

    stages {
        stage('Build') {
            steps {
                echo 'from Build stage..'
            }
        }
        stage('Test') {
            steps {
                echo 'from Testing.. stage'
                sleep 10
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
            echo 'All stages are successful'
        }

        failure { 
            echo 'from the failure block of post'
        }

    }
    
}