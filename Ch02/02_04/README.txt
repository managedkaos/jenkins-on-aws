Enter the following into the User Data form:

    #!/bin/bash
    # update the yum cache
    yum update

    # install java
    yum -y install java-1.8.0-openjdk

    # install git
    yum -y install git

    # install the elastic beanstalk CLI
    /usr/bin/easy_install awsebcli

