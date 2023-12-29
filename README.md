# Jenkins-CICD-GamePlay

![image](https://github.com/forza-dc/Jenkins-CICD-GamePlay/assets/37484962/76f1333f-2381-4da9-a874-2986c9022b0c)


Ansible Playbook for Jenkins and EC2 Provisioning
This folder contains Ansible scripts for automating the installation of Jenkins and provisioning an EC2 instance with a specified security group.

Files:
1. jenkins-playbook.yml
This Ansible playbook installs Jenkins on the localhost. The tasks performed include:

Updating all packages to their latest version.
Downloading the Jenkins GPG key.
Adding the Jenkins repository.
Installing necessary dependencies (fontconfig and Java).
Installing Jenkins using apt.
Ensuring the Jenkins service is started and enabled.

2. Jenkinsfile
This Jenkins Pipeline file defines a set of stages to be executed in Jenkins. The stages include:

cleanws: Cleans the workspace.
checkout: Checks out the source code from the specified GitHub repository.
TRIVY FS SCAN: Performs a vulnerability scan on the file system using Trivy.
ansible provision: Executes the Ansible playbook ec2.yaml using the Ansible Jenkins plugin.
3. ec2.yaml
This Ansible playbook provisions a new EC2 instance on AWS. The tasks include:

Installing necessary Python dependencies using pip.
Creating an EC2 security group with specified rules.
Launching a new EC2 instance with a user data script to install Docker and run a container.

Instructions:
Ensure Ansible is installed on the localhost where the playbook is intended to run.
Make sure Jenkins is configured with the necessary plugins, including the Ansible plugin.
Configure Jenkins credentials for Ansible (e.g., ansible).
Customize variables in the ec2.yaml file, such as keypair, instance_type, image_id, etc., to match your AWS environment.
Create a new Jenkins job, configure it to use the Jenkinsfile, and specify the necessary parameters.
By using these scripts, you can automate the installation of Jenkins and provision EC2 instances with security groups for your applications.
