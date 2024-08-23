### JENKINS
- jenkins is a continues intigration tool
#### SETUP
* go to jenkins.io select centos
* to install jenkins use below command
```jenkins
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key  
sudo yum install fontconfig java-17-openjdk -y
sudo yum install jenkins -y
sudo systemctl start jenkins
sudo systemctl status jenkins
sudo systemctl enable jenkins
```
* junkins runs at 8080 port number
* browse **IP_ADDRESS:8080** you san see password/path cat password/path copy it and paste it at jenkins install reqied plugins
```jenkins
/var/lib/jenkins/secrets/initialAdminPassword
cat /var/lib/jenkins/secrets/initialAdminPassword
```
* everything in jenkins is a job there are two types of jobs 
    1. freestyle
    2. pipeline

1. freestyle
    * it is nothing but doing everything in UI
    * it has both advantages and disadvantages
* **disadvantages**
    * here we dont undastand who did what change it is very deficult to restore back to the narmal stage
    * thats the reson why we switched to pipeline now nobody is using freestyle

2. pipeline
    * one jenkins server cannot handle all the load it may hang thats is the reason
    * it contains **master agent or node architecture**
    * jenkins master responsibulity is to distibute the load to multipule agents then overview that job
    * list all nodes and connecting to node as below 
        * **dashboard ===> manage jenkins ===> nodes ===> click on new node ===> name it ===> no.of.executions ===> remote root directory ===> labels ===> launch mathod ===>   host ===> credentials ===> click on save**
    * **no.of.executions** how many jobs that agent should run at a time 
    * **remote root directory** it is the path/of/data related to builts or jobs 
    * **labels** it is nothing but tag names ex:- agent-1
    * **launch mathod** there are two methods here
      1. employ can ask master for work
        * **employe is connecting to master**
      2. when there is a work master can ask employee to do 
        * **master is connecting to employe**
    * **host** given agent ip_address
    * **credentials** give user_name and passsword details of your os we use here centos
* **jenkins is devloped on java we need to install java in both master and agent**
```
sudo yum install fontconfig java-17-openjdk -y
```
- there are two types of pipeline
1. decleretive pipeline
2. scripted pipeline
- decleretive is the latest version pf pipeline in jenkins
* **BASIC SYNTAX**
```Jenkins
pipeline {
    agent any


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
}
```
* pipeline is of two types
1. pipeline script
2. pipeline script from SCM (Git)
* **multypule sections in pipeline**
1. Agent
    1. any
    * Execute the Pipeline, or stage, on any available agent. 
    For example: agent any
* to add particular agent use below syntax
```Jenkins
agent { node { label 'labelName' } }
```
**example**
agent { node { label 'AGENT-1' } }
* but node allows for additional options (such as customWorkspace).





