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
        string (name: 'age', defaultValue: "26", description: 'giveing my age details' )
        choice (name: 'Name', choices: ['manu', 'hari', 'shiva', 'mahesh'], description: 'giveing my age details')
        booleanParam (name: 'condition', defaultValue: true, description: 'giveing boolean value')
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
            }
        } 

        stage('Environment') {
            steps {
                echo "using environment variable"
                sh '''
                echo "${GREETING}"
                '''
            }
        }

        stage('Parameters') {
            steps {
                echo "using parameter variable"
                echo "my name is ${params.Name} my age is ${params.age} iam married? ${params.condition}"
                echo "${Person}"
            }
        } 

        stage('Groovy script') {
            script{
                def Person = "${params.Name}"
            }
            steps {
                echo "using parameter variable"
                echo "my name is ${params.Name} my age is ${params.age} iam married? ${params.condition}"
                echo "${Person}"
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
