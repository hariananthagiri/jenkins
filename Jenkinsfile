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
                    sh '''
                    echo 'displaying environment variable'
                    echo "${GREETING}"
                    echo env
                    '''
                }
        }
    //     stage('parameters') {
    //         steps {
    //             echo 'Parameters....'
    //              echo "${params.PERSON}"
    //         }
    //     }
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
