pipeline {
    agent { node { label 'AGENT-1' } }

    stages {
        stage('Build') {
            steps {
                echo "Building...."
            }
        }
        stage('Test') {
            steps {
                echo "Testing...."
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying...."
            }
        }
    }
    post { 
        always { 
            echo 'It will whethere job is sucess or not'
        }
        success { 
            echo 'It will whethere job is sucess'
        }
        failure { 
            echo 'It will whethere job is failure'
        }    
    }     
}
