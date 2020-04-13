Step 1.  Launch an instance (Amazon Linux) 

Step 2.  Login to the instance, install and setup java environment 

sudo yum install -y git  java-1.8.0-openjdk-devel aws-cli

sudo alternatives --config java

In this command change version of java to the latest version.

Step 3. Install Apache Maven 

sudo wget http://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo

sudo sed -i s/\$releasever/6/g /etc/yum.repos.d/epel-apache-maven.repo

sudo yum install -y apache-maven

mvn –v

Step 4.  Install Jenkins 

sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat/jenkins.repo

sudo rpm --import http://pkg.jenkins-ci.org/redhat/jenkins-ci.org.key

sudo yum install jenkins

sudo service jenkins start

sudo chkconfig --add jenkins

That’s it! Now you can go to URL http://<instance ip>:8080

If you’re unable to see the Jenkins page, check security groups restrictions. You can also change the port for Jenkins manually if you want to run it on a different port.

Step 5. Setup Jenkins

This is the first screen you will after going to http://<instance ip>:8080

screen-1-jenkins
go to file/var/lib/jenkins/secrets/initialAdminPassword , copy the password and paste it in “administrator password” input box. Then press continue.

 

screen2-jenkins-plugins
On this page select default option “Install suggested plugins”
Next, you will see above the screen. Select install suggested plugins.

screen-3-jenkins-install-plugins
Select plugins to install
Next, it will ask for admin credential. You can skip this step and click on continue as admin or you can fill in the required information.

screen-4-create-admin-user
 

Jenkins will be installed.. you will see a welcome page something like this.

screen-5-welcome-screen
Welcome page
 

That’s it!  you’ve successfully installed Jenkins on Amazon Linux (AWS)

Please comment below your queries and I’ll surely love to help out.
