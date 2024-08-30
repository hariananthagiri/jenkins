pipeline {
    agent { 
        node { 
            label 'AGENT-1' 
        } 
    }
    environment {
        GREETING = "hello jenkins"
    }
    // build
    stages {
        stage('Build') {
            steps {
                echo 'Building....'
            }
        }
        stage('Test') {
            input {
                message "should we continue?"
                ok "yes, we should." 
            }
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
            input {
                message "should we continue?"
                ok "yes, we should." 
            }
            steps {
                echo 'Deploying....'
                sh '''
                    ls -ltr
                    pwd
                    '''
            }
        }
    
        stage('environment') {
            steps {
                echo "using environment variable"
                sh '''
                echo "${GREETING}"
                printenv
                '''
            }
        }
    }
    // post build
    post { 
        always { 
            echo 'It will run whethere job is sucess or not'
            deleteDir()
        }
        success { 
            echo 'It will run whethere job is sucess'
        }
        failure { 
            echo 'It will run whethere job is failure'
        }    
    }     
}
