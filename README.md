# Ansible Web Application Deployment on AWS

Welcome to my Ansible web application deployment project! This project showcases how to use Ansible for automating the deployment of a simple web application on an AWS EC2 instance. It includes provisioning the EC2 instance, installing necessary software (Nginx), deploying a web application, and configuring the server.

## Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Setup Instructions](#setup-instructions)
- [Deployment](#deployment)
- [Accessing the Web Application](#accessing-the-web-application)
- [Troubleshooting](#troubleshooting)
- [Common Issues](#common-issues)
- [Logs](#logs)
- [Contributing](#contributing)
- [License](#license)

## Project Overview

This project automates the deployment of a web application using Ansible. It provisions an AWS EC2 instance, installs Nginx, and serves a simple HTML page. The project demonstrates the power of Ansible in managing infrastructure and deploying applications efficiently.

## Features

- **Automated Deployment**: Provision EC2 instance, install Nginx, and deploy web application using Ansible.
- **Infrastructure as Code**: Manage infrastructure and configurations with Ansible playbooks.
- **Scalability**: Easily modify and extend the playbooks for more complex deployments.

## Technologies Used

- **Ansible**: Automation tool for IT tasks.
- **AWS EC2**: Cloud computing service for running virtual servers.
- **Nginx**: Web server to serve the HTML page.
- **SSH**: Secure shell for accessing and managing the EC2 instance.

## Setup Instructions

Follow these steps to set up and deploy the project:

### Prerequisites

- [AWS account](https://aws.amazon.com/)
- [Ansible installed](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
- [Git installed](https://git-scm.com/)
- SSH key pair for accessing EC2 instances

### Step 1: Clone the Repository

1. Clone the repository to your local machine:
    ```bash
    git clone https://github.com/yourusername/project_ansible.git
    cd project_ansible
    ```

### Step 2: Configure Ansible

1. Edit the `ansible.cfg` file to set up the configuration for your environment.
2. Edit the `inventory.ini` file to include the public IP address of your EC2 instance:
    ```ini
    [web]
    <your-ec2-public-ip> ansible_ssh_private_key_file=<path-to-your-pem-file> ansible_user=ubuntu
    ```

### Step 3: Create index.html

1. Create an `index.html` file with the content you want to serve:
    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <title>Welcome to My Web App</title>
    </head>
    <body>
        <h1>Hello, World!</h1>
        <p>This is a simple web application deployed using Ansible.</p>
    </body>
    </html>
    ```

### Step 4: Create Ansible Playbook

1. Create a `deploy.yml` file with the necessary tasks to deploy the web application.

### Step 5: Run the Playbook

1. Run the Ansible playbook to deploy the web application:
    ```bash
    ansible-playbook -i inventory.ini deploy.yml
    ```

## Deployment

After running the playbook, your web application should be deployed on the AWS EC2 instance and accessible via its public IP address.

## Accessing the Web Application

Open a web browser and navigate to the public IP address of your EC2 instance to see the deployed web application.

http://<your-ec2-public-ip>
Troubleshooting
Common Issues
Nginx Not Running: Ensure Nginx is installed and running. Use sudo service nginx start to start Nginx.
Firewall/Security Group: Ensure that the security group associated with your EC2 instance allows inbound traffic on port 80 (HTTP).
Permission Issues: Ensure the Ansible user has the necessary permissions to access the EC2 instance and modify files.
Logs
Nginx Logs: Check the Nginx logs for errors.

sudo tail -f /var/log/nginx/error.log
System Logs: Check system logs for any other issues.

sudo tail -f /var/log/syslog
Contributing
If you would like to contribute to this project, please fork the repository and submit a pull request with your proposed changes.

License
This project is licensed under the MIT License - see the LICENSE file for details.
