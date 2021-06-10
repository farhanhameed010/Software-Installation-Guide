# Jenkins Master And Slave Installtion Guide

## Jenkins Master Instance:-  
Install Java 1.8 and Jenkins Both
## Jenkins Slave Instance:-
Only need to install java 1.8

## How to install Java:-
To ensure that your software packages are up to date on your instance, use the following command to perform a quick software update

>  $ sudo yum update -y 

Run below commands to install Java 8 on Amazon Linux

> $ sudo yum install java-1.8*

Check Active Java Version
> $ java -version

## Download and install Jenkins

Add the Jenkins repo using the following command

> $ sudo wget -O /etc/yum.repos.d/jenkins.repo \ https://pkg.jenkins.io/redhat-stable/jenkins.repo

Import a key file from Jenkins-CI to enable installation from the package
> $ sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
>
> $ sudo yum upgrade

Install Jenkins

> $ sudo yum install  jenkins  -y

Start Jenkins as a service

> $ sudo systemctl start jenkins

You can check the status of the Jenkins service using the command
> $ sudo systemctl status jenkins

## Configure Jenkins

Use the following command to display this password

> $ sudo cat /var/lib/jenkins/secrets/initialAdminPassword

After enter the password setup username and password

## Configure Slave Instance:- <br>

First of all create the SSH-key Pairs though PuttyGen Or other method<br>
Copy Public Key Slave Instance in .SSH Directory in authorized_keys file below  command show the hide directory 
> $ ls -la


## Goto the jenkins Dashboard <br>

Click  **Manage nodes** and Cloud than Click **New Node** <br>
*Number Executors* like (5) <br>
*Remote root Directory* like  (/home/ec2-user/slave1) <br>
*launch method* select Launch agents via  SSH  <br>
*Host* Slave Machine name like (ec2-3-141-13-155.us-east-2.compute.amazonaws.com) <br>
*Host Key Verification Strategy*:- Manually trusted Key Verification Strategy <br> 
Than add the Credentials to Connect the slave Machine before create private key  as a crediatials <br> 
**Add Credentials** through *Kind* (SSH Username with private Key)