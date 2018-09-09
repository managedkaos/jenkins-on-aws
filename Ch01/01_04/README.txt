Change to the root user after logging in:

    sudo su -

Add the aptitude key for the Jenkins application:

	wget http://pkg.jenkins-ci.org/debian-stable/jenkins-ci.org.key
	apt-key add jenkins-ci.org.key

Add the Jenkins debian repo to the aptitude sources list:

     echo "deb http://pkg.jenkins-ci.org/debian binary/" > /etc/apt/sources.list.d/jenkins.list

Update the source lists and upgrade any out of date packages:

    apt update
    apt upgrade

Install the software for the Jenkins master:  openjdk-8-jdk, nginx, and jenkins.

    apt install -y openjdk-8-jdk
    apt install -y nginx
    apt install -y jenkins

Confirm that jenkins and nginx are installed:

    systemctl status nginx | grep Active
    systemctl status jenkins | grep Active

