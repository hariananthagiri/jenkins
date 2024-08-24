pipeline {
    agent { node { label 'AGENT-1' } }
    
    stages {
        stage('Build') {
            steps {
                echo 'Building....'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing2....'
                    sh '''
                    ls -ltr
                    pwd
                    whoami
                    '''
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying1....'
            }
        }
    }
    post { 
        always { 
            echo 'It will run whethere job is sucess or not'
        }
        success { 
            echo 'It will run whethere job is sucess'
        }
        failure { 
            echo 'It will run whethere job is failure'
        }    
    }     
}
