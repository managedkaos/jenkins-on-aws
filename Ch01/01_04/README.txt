Change to the root user after logging in:

    sudo su -

Add the aptitude key for the Jenkins application:

	wget https://pkg.jenkins.io/debian-stable/jenkins.io.key
	apt-key add jenkins.io.key

Add the Jenkins debian repo to the aptitude sources list:

     echo "deb http://pkg.jenkins.io/debian-stable binary/" > /etc/apt/sources.list.d/jenkins.list

Update the source lists and upgrade any out of date packages:

    apt update
    apt -y upgrade

Install the software for the Jenkins master:  openjdk-8-jdk, nginx, and jenkins.

    apt install -y openjdk-8-jdk
    apt install -y nginx
    apt install -y jenkins

Confirm that jenkins and nginx are installed:

    ps -elf | grep nginx
    ps -elf | grep jenkins
