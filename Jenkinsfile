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
                bulildjob: "pipeline-2", wait: true
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
            // input {
            //     message "should we continue?"
            //     ok "yes, we should." 
            // }
            steps {
                echo 'environment variable'
                sh '''
                echo "${GREETING}"
                echo env
                '''
            }
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
