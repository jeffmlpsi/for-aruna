Before running: 
a) create a security group in us-west-1 named: test
b) make sure you have an ssh key from us-west-1 and you know where it is on your machine
c) Install Python 3.9 or later
d) Install boto3, the Python API for AWS, with pip3
e) install paramiko, the ssh API for Python, with pip3
f) Make sure your AWS SSO user is active by running: aws configure sso. 
Make sure you name you AWS SSO profile iam-profile, since that is used in the code.

To run: 
a) run.sh:              python3 st34.py "test" TestKeyPair-US-West-2 ./keypairs
or
b) run-and-delete.sh:   python3 st34.py "test" TestKeyPair-US-West-2 ./keypairs -d

Change to keypair file name to match what is on your system. And, the path to the folder that contains the keypairs.

In Visual Studio Code you can create debug configuration in launch.json for your project. Fosr example:

{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "name": "st34.py, Python Debugger: Current File",
            "type": "debugpy",
            "request": "launch",
            "program": "st34.py",
            "console": "integratedTerminal",
            "args": ["test", "TestKeyPair-US-West-2","./keypairs"]
        },
        {
            "name": "st34.py delete on exit Python Debugger: Current File",
            "type": "debugpy",
            "request": "launch",
            "program": "st34.py",
            "console": "integratedTerminal",
            "args": ["test", "TestKeyPair-US-West-2","./keypairs","-d"]
        }
    ]
}

