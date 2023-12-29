# Super Mario Bros meets Ansible, Jenkins, and Kubernetes

![image](https://github.com/forza-dc/Jenkins-CICD-GamePlay/assets/37484962/76f1333f-2381-4da9-a874-2986c9022b0c)

This project uses Ansible, Jenkins, AWS EKS to run a version of the popular Super Mario game.



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



Disclaimer:

Disclaimer:

This project includes images from Nintendo Corporation Ltd's Super Mario game, which are used solely for educational purposes in an Ansible, Jenkins, and Amazon EKS (Elastic Kubernetes Service) demonstration. The inclusion of these images is intended to illustrate concepts related to configuration management, continuous integration, and cloud orchestration.

Fair Use Act:

This usage falls under the provisions of the Fair Use Act as it is for educational purposes, non-commercial in nature, and does not adversely affect the market for the original work. The images are employed to enhance the understanding of Ansible, Jenkins, and EKS concepts within the context of a demonstration project.

Credit:

The Ansible playbook and Jenkinsfile in this project incorporate code from the Aj7Ay GitHub repository. We extend our gratitude and acknowledgment to the contributors of the XYZ repository for their valuable code contributions. The use of their code enhances the functionality and completeness of this demonstration project. For more details, please refer to the Aj7Ay's repository at https://github.com/Aj7Ay/k8s-mario.






