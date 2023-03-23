# Jenkins Installation on RHEL

### You can execute this script as user-data when launching your EC2 VM 

 ## Set time zone for your instance 
 
``` sudo timedatectl set-timezone America/New_York ```

#### Set *Jenkins-hostname* and download Jenkins Software

``` sudo hostnamectl set-hostname jenkins 
sudo wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
sudo dnf upgrade
```

#### Add required dependencies for the jenkins package

```
sudo dnf install java-11-openjdk
sudo dnf install jenkins
sudo systemctl daemon-reload
```
### Start Jenkins
#### You can enable the Jenkins service to start at boot with the command:

``` sudo systemctl enable jenkins
```
#### You can start the Jenkins service with the command:

``` sudo systemctl start jenkins
```
#### You can check the status of the Jenkins service using the command:

``` sudo systemctl status jenkins ```
