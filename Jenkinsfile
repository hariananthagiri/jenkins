pipeline {
    agent { 
        node { 
            label 'AGENT-1' 
        } 
    }
    environment {
        GREETING = "hello jenkins"
    }
    options {
        ansiColor('xterm')
    }
    // build
    stages {
        stage('Build') {
            steps {
                echo 'Building....'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing....'
                    sh '''
                    ls -ltr
                    pwd
                    env
                    '''
            }
        }  
        stage('Deploy') {
            steps {
                echo 'Deploying1....'
                sh '''
                    ls -ltr
                    pwd
                    '''
            }
        }
    }
     stage('environment') {
            steps {
                sh '''
                echo 'displaying environment variable'
                echo "${GREETING}"
                echo env
                '''
            }
        }
    }
    stage('Deploy') {
            steps {
                echo 'Deploying1....'
                sh '''
                    ls -ltr
                    pwd
                    '''
            }
    }
    
    // post build
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
