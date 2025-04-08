
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
TASK 2: Create a Simple Jenkins Pipeline for CI/CD
Objective: Set up a basic Jenkins pipeline to automate the process of building and deploying an
application.
Tools: Jenkins, Docker
Deliverables: A Jenkins pipeline file (Jenkinfile) to build and deploy an app.
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Steps to work for this problem is as :-

1. Create an EC2 instance.
2. Install Jenkins & Java (JDK) from steps below..
3. Run the below commands to install Java and Jenkins
sudo apt update
sudo apt install openjdk-17-jre
4. Now, you can proceed with installing Jenkins

curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins

5. Jenkins will not be accessible to the external world due to the inbound traffic restriction by AWS. Open port 8080 in the inbound traffic rules as show below.

EC2 > Instances > Click on
In the bottom tabs -> Click on Security
Security groups
Add inbound traffic rules as shown in the image (you can just allow TCP 8080 as well, in my case, I allowed All traffic).

6. After you login to Jenkins, - Run the command to copy the Jenkins Admin Password - sudo cat /var/lib/jenkins/secrets/initialAdminPassword - Enter the Administrator password

7. Install the necessary suggested plugins

8. Install the Docker Pipeline plugin in Jenkins:
Log in to Jenkins.
Go to Manage Jenkins > Manage Plugins.
In the Available tab, search for "Docker Pipeline".
Select the plugin and click the Install button.
Restart Jenkins after the plugin is installed.

9. Wait for the Jenkins to be restarted.

Docker Slave Configuration
Run the below command to Install Docker

sudo apt update
sudo apt install docker.io

10. Grant Jenkins user and Ubuntu user permission to docker deamon.
sudo su - 
usermod -aG docker jenkins
usermod -aG docker ubuntu
systemctl restart docker

11. Once you are done with the above steps, it is better to restart Jenkins.

http://<ec2-instance-public-ip>:8080/restart

12. Inside jenkins select the option of new project and select pipeline option.

13. Then paste the github url save and hence the build is successfull.
