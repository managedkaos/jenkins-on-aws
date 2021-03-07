Enter the following script into an Execute Shell build step to deploy your
elastic beanstalk application:

    #!/bin/bash -xe

    # intialize the application
    eb init my-eb-app2 --platform python-3.6 --region us-west-2

    # select the development environment
    eb use development

    # deploy the application
    eb deploy

    # get the deployment's health and status information
    eb health
    eb status
