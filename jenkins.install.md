## Step 2: Install Java
```sh 
sudo yum update -y
sudo yum install java-17-amazon-corretto -y
```
## Verify:
```sh
java -version
```
## Step 3: Install Jenkins
```sh
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
sudo yum install jenkins -y
```
## Step 4: Start Jenkins
```sh
sudo systemctl start jenkins
sudo systemctl enable jenkins
```
Check:
```sh
sudo systemctl status jenkins
```
## Step 6: Access Jenkins
```sh
http://<EC2-Public-IP>:8080
```
## Step 7: Get Admin Password
```sh
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
