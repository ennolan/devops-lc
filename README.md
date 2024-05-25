# DevOps Lifecycle Project

The following are the specifications of the lifecycle: 

1. Install necessary software on the machines using a configuration management tool.
2. Git workflow has to be implemented.
3. The code should be containerized with the help of a Dockerfile. The Dockerfile should be built every time there is a push to GitHub. The code should reside in '/var/www/html' 
4. The above tasks should be defined in a Jenkins Pipeline with the following jobs: 
a. Job1: build 
b. Job2: test 
c. Job3: prod
5. Code Build should automatically be triggered once a commit is made to main branch or patch branch. 
a. If a commit is made to main branch, test and push to prod 
b. If a commit is made to patch branch, just test the product, do not push to prod


# Process briefing:

In this project, we need to install “Java”, “Jenkins”, “Ansible”, “Docker” & “Python” on “Master” instance while we install “Java” & “Docker” on both Slave instances. 

We don’t need to create Job1, “build” here as we are not integrating an actual application yet. Only “test” & “prod” will do the jobs.

A. Create three Linux instances named Master, Slave1 & Slave2 respectively.

B. Install “Ansible” on Master machine using “install.sh” file

C. Run the “install.sh” file using the command: bash install.sh

D. Create the keys to “Master” instance & copy into "authorized keys" file of “Slave1” & “Slave2” each.

E. Copy the Slave1 and Slave2 IP addresses into the “Ansible Host File”

F. Run this ansible command to ping the machines: ansible -m ping all.
Type “Yes” & your “slaves” will be successfully pinged.

G. Create a yaml file to run “master.sh” & “slave.sh” file to install needed tools on the instances.

H. Run this command to create an “ans.yaml” file to execute the “master.sh” & “slave.sh” through “Ansible”. Command: sudo nano ans.yaml 

I. Create “master.sh” & “slave.sh” file to install Much needed tools on the instances
 
J. Type this command to execute the “master.sh” & “slave.sh” using “ans.yaml” file.
ansible-playbook ans.yaml 

All the mentioned tools in “master” & “slaves” have been successfully installed, if status is “Ok”.
 
K. Verified All Tools Have Been Successfully Installed on Master & Slaves or Not

L. Setup Jenkins Dashboard Over “Master” Server 

M. Add “Slave1” in “Jenkins”

N. Add “Slave2” in “Jenkins”

# More later...