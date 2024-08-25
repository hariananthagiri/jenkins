pipeline {
    agent { 
        node { 
            label 'AGENT-1' 
        } 
    }
    environment {
        GREETING = "hello jenkins"
    }
    parameters {
    string(name: 'PERSON', defaultValue: 'hari krishna', description: 'writeing my name')
    }
    // options {
    //     ansiColor('xterm')
    // }
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
        stage('parameters') {
            steps {
                echo 'Parameters....'
                sh '''
                    echo "${params.PERSON}"
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
