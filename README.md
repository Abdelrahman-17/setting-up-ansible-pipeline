
# Ansible Automation for Application Deployment

This repository contains Ansible playbooks and roles for automating the deployment of a sample "Hello World" application. Follow the tasks below to set up and deploy the application.

## Tasks

### 1. Install and Configure Ansible
- Set up Ansible on your local machine or an Ubuntu server.
- Ensure you have SSH access to the target server.
- Configure the Ansible inventory file with the target host.

### 2. Clone Sample Application
- Clone the sample 'Hello World' application from this GitHub repository: [python-getting-started](https://github.com/heroku/python-getting-started).

### 3. Write Ansible Playbooks
- Create a playbook to set up the environment (e.g., install necessary packages like Python, Git).
- Create a playbook to deploy the sample application from the cloned repository.
- Ensure the playbooks include tasks for starting and stopping the application.

### 4. Create Ansible Roles
- Organize tasks into roles for better reusability and maintainability.
- Create roles for common tasks such as environment setup and application deployment.

### 5. Test Ansible Playbooks
- Run the playbooks on a test Ubuntu server.
- Validate that the environment is set up correctly and the application is deployed successfully.

### 6. Document Ansible Playbooks
- Write clear documentation for each playbook and role.
- Include instructions on how to run the playbooks and any prerequisites.

## Setup Instructions

1. **Install and Configure Ansible:**
   - Install Ansible:
     ```bash
     sudo apt update
     sudo apt install ansible
     ```
   - Ensure SSH access to the target server:
     ```ini
     ssh-keygen -t rsa -b 2048
     ```
   - to save your key (default is usually ~/.ssh/id_rsa). Then, copy the public key to your target server:  
     ```ini
     ssh-copy-id user@target_server_ip
     ```
   - Configure the inventory file (`hosts.ini`):
     ```ini
     [webservers]
     your_target_server_ip ansible_user=your_username 
     ```
     ![WhatsApp Image 2024-07-02 at 10 59 52 PM](https://github.com/Abdelrahman-17/setting-up-ansible-pipeline/assets/83679041/c686b6a1-a24a-43a9-96a7-432e4adf6ed0)
   - Configure Ansible to Use SSH Keys:
       By default, Ansible uses SSH to connect to the managed nodes. Ensure Ansible is using your SSH key by checking your `ansible.cfg` configuration file. If you don't have an ansible.cfg file, create one in your project directory:

      ```ini
      [defaults]
      inventory = hosts.ini

      [ssh_connection]
      ssh_args = -o ForwardAgent=yes -o ControlMaster=auto -o ControlPersist=60s

     ```

     ![WhatsApp Image 2024-07-02 at 10 59 51 PM](https://github.com/Abdelrahman-17/setting-up-ansible-pipeline/assets/83679041/9da6b366-2f45-466f-b817-b81f590fac82)
   - Test SSH Access with Ansible:
     Use the ansible command to test connectivity to your target server:
     ```ini
      ansible all -m ping -i hosts.ini
     ```
     ![WhatsApp Image 2024-07-02 at 10 59 53 PM](https://github.com/Abdelrahman-17/setting-up-ansible-pipeline/assets/83679041/4ae1c5eb-3b23-4378-af66-0f6341762b2d)


2. **Clone Sample Application:**
   - Clone the repository:
     ```bash
     git clone https://github.com/heroku/python-getting-started.git
     cd python-getting-started
     ```

3. **Write Ansible Playbooks:**
   - Create `setup_environment.yml` to install necessary packages.
   - Create `deploy_application.yml` to deploy the sample application.

4. **Create Ansible Roles:**
   - Create a role for setting up the environment (`environment_setup`).
     ```bash
      ansible-galaxy init environment_setup

     ```
   - Then move the Tasks from setup_environment.yml and put it inside the Tasks inside the main.yml file.

    
   - Create a role for deploying the application (`application_deployment`).
      ```bash
      ansible-galaxy init application_deployment


     ```
      
   - Then move the Tasks from deploy_application.yml and put it inside the Tasks inside the main.yml file.



5. **Test Ansible Playbooks:**
   - Run the playbooks:
     ```bash
     ansible-playbook -i hosts.ini setup_environment.yml  --ask-become-pass
     ansible-playbook -i hosts.ini deploy_application.yml  --ask-become-pass
     ```

     ![WhatsApp Image 2024-07-03 at 10 29 15 PM](https://github.com/Abdelrahman-17/setting-up-ansible-pipeline/assets/83679041/2fb22f56-c582-4dcf-a9e0-c12160c1cd3e)


     ![WhatsApp Image 2024-07-03 at 10 29 14 PM](https://github.com/Abdelrahman-17/setting-up-ansible-pipeline/assets/83679041/be21b6a4-5774-4fc7-a0a4-b591e82103b8)


   - Then you can run the site via port tcp/5000 

     ![WhatsApp Image 2024-07-03 at 10 28 49 PM (1)](https://github.com/Abdelrahman-17/setting-up-ansible-pipeline/assets/83679041/0fe00b42-2c09-477f-ae7a-4c1ea9a54aee)




6. **Document Ansible Playbooks:**
   - Include documentation in the README.md for each role and playbook


