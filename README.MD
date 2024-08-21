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