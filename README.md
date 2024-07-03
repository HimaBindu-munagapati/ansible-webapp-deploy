Ansible Web Application Deployment on AWS
This project demonstrates how to use Ansible to automate the deployment of a simple web application on an AWS EC2 instance. It covers provisioning the EC2 instance, installing necessary software (Nginx), deploying a web application, and configuring the server.

**Table of Contents**
Introduction
Prerequisites
Project Structure
Setup Instructions
Deployment Steps
Accessing the Web Application
Troubleshooting
License
Introduction
This project automates the deployment of a web application using Ansible. It provisions an AWS EC2 instance, installs Nginx, and serves a simple HTML page. The project showcases the power of Ansible in managing infrastructure and deploying applications efficiently.

**Prerequisites**
Before you begin, ensure you have the following:

An AWS account with permissions to create EC2 instances.
An SSH key pair for accessing the EC2 instance.
Ansible installed on your local machine.
Git installed on your local machine.
**Project Structure**
The project directory contains the following files:
project_ansible/
ansible.cfg
deploy.yml
index.html
inventory.ini
ansible.cfg: Configuration file for Ansible.
deploy.yml: Ansible playbook to provision and configure the EC2 instance.
index.html: Simple HTML file to be served by Nginx.
inventory.ini: Inventory file containing the target EC2 instance.
**Setup Instructions**
1. Clone the Repository
Clone the project repository to your local machine:
git clone https://github.com/yourusername/project_ansible.git
cd project_ansible
2. Configure Ansible
Edit the ansible.cfg file to set up the configuration for your environment.
3. Set Up Inventory
Edit the inventory.ini file to include the public IP address of your EC2 instance:
<your-ec2-public-ip> ansible_ssh_private_key_file=<path-to-your-pem-file> ansible_user=ubuntu
4. Provision and Configure EC2 Instance
Run the Ansible playbook to provision and configure the EC2 instance:
ansible-playbook -i inventory.ini deploy.yml
**Deployment Steps**
Provision EC2 Instance: Ansible will use the AWS module to create an EC2 instance.
Install Nginx: The playbook installs Nginx on the EC2 instance.
Deploy Web Application: The HTML file (index.html) is copied to the Nginx root directory.
Configure Nginx: Nginx is configured to serve the HTML file.
**Accessing the Web Application**
After the playbook completes, open a web browser and navigate to the public IP address of your EC2 instance. You should see the content of the index.html file.
http://<your-ec2-public-ip>
**Troubleshooting**
**Common Issues**
Nginx Not Running: Ensure Nginx is installed and running. Use sudo service nginx start to start Nginx.
Firewall/Security Group: Ensure that the security group associated with your EC2 instance allows inbound traffic on port 80 (HTTP).
Permission Issues: Ensure the Ansible user has the necessary permissions to access the EC2 instance and modify files.
Logs
Nginx Logs: Check the Nginx logs for errors.
sudo tail -f /var/log/nginx/error.log
System Logs: Check system logs for any other issues.
sudo tail -f /var/log/syslog
**License**
This project is licensed under the MIT License. See the LICENSE file for details.
