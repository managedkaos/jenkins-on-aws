To create the build server, start on the EC2 Dashbaord.

1. Click "Launch Instance"
2. On step 3 of the launch wizard, "Step 3: Configure Instance Details", click "Advanced Details"
3. Enter the following into the User Data form:

    #!/bin/bash
    # install dependencies
    yum group install "Development Tools" -y
    yum install zlib-devel openssl-devel ncurses-devel libffi-devel sqlite-devel.x86_64 readline-devel.x86_64 bzip2-devel.x86_64 -y

    # install the elastic beanstalk CLI
    su - ec2-user -c "git clone https://github.com/aws/aws-elastic-beanstalk-cli-setup.git /tmp/aws-elastic-beanstalk-cli-setup"
    su - ec2-user -c "/tmp/aws-elastic-beanstalk-cli-setup/scripts/bundled_installer"
    su - ec2-user -c "echo 'export PATH=\"~/.pyenv/versions/3.7.2/bin:~/.ebcli-virtual-env/executables:$PATH\"' >> ~/.bash_profile"