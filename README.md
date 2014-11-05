# opsworks-deploy #

Shell script to initiate OpsWorks application deployments using AWC CLI scripts.
We use this script as part of our continuous deployment to initiate the deployment
on OpsWorks and then monitor for the results.

After initiating a deployment it will continue to check the status of that deployment
and monitor for success or fail. The script will exit with status ```0``` on success.

We're open to enhancements so please submit pull requests or ideas if you have them.
So far this is pretty quick and dirty, but works pretty well.

Usage:

    ./opsworks-deploy <aws-region> <stack-id> <application-id>


Example:

    $ ./opsworks-deploy us-east-1 1234-sdfhjkuytfdcxswerfgvbnk-23456 2234-akflshfiwefjnfsfdsdffs-111
    Deployment initiated, ID: 12f01234441-6fsb-4b70-8bba-43012312374c
    Attempt #0 of 30...
    Current Status: running
    Attempt #1 of 30...
    Current Status: running
    Attempt #2 of 30...
    Current Status: running
    Attempt #3 of 30...
    Current Status: running
    Attempt #4 of 30...
    Current Status: running
    Attempt #5 of 30...
    Current Status: running
    Attempt #6 of 30...
    Current Status: running
    Current Status: successful
    Deployment completed successfully!

## AWS CLI tools ##
This script makes use of the Amazon Web Services command line interface tools. They can
be installed by running ```pip install awscli```. The tool expects environment variables
to be set for ```AWS_ACCESS_KEY_ID``` and ```AWS_SECRET_ACCESS_KEY```. These you get from
AWS when you create a deployment IAM user.