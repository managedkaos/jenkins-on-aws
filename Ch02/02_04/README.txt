Enter the following into the User Data form:

    #!/bin/bash

    # install dependencies
    apt -y install build-essential zlib1g-dev libssl-dev libncurses-dev libffi-dev libsqlite3-dev libreadline-dev libbz2-dev

    # install java
    apt -y install openjdk-11-jdk

    # install the elastic beanstalk CLI
    wget https://bootstrap.pypa.io/get-pip.py
    python3 ./get-pip.py
    pip install --upgrade pip
    pip install virtualenv
    git clone https://github.com/aws/aws-elastic-beanstalk-cli-setup.git
    python3 aws-elastic-beanstalk-cli-setup/scripts/ebcli_installer.py  --location /usr/local/bin
    ln -s /usr/local/bin/.ebcli-virtual-env/executables/eb /usr/local/bin/eb
    ln -s /usr/bin/python3 /usr/local/bin/python

    # test installation
    which python && python --version
    which eb && eb --version