
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
   - Ensure SSH access to the target server.
   - Configure the inventory file (`hosts.ini`):
     ```ini
     [webservers]
     your_target_server_ip ansible_user=your_username ansible_ssh_pass=your_password ansible_become_pass=your_sudo_password
     ```

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
   - Create a role for setting up the environment (`roles/setup_environment`).
   - Create a role for deploying the application (`roles/deploy_application`).

5. **Test Ansible Playbooks:**
   - Run the playbooks:
     ```bash
     ansible-playbook -i hosts.ini setup_environment.yml
     ansible-playbook -i hosts.ini deploy_application.yml
     ```

6. **Document Ansible Playbooks:**
   - Include documentation in the README.md for each role and playbook.

## Example Playbook

### `setup_environment.yml`
```yaml
---
- name: Setup Environment
  hosts: webservers
  become: yes
  roles:
    - setup_environment















. **ملف `setup_environment/README.md`**:
2. 

   - انتقل إلى مجلد `setup_environment`:
     ```bash
     cd setup_environment
     ```
   - إنشاء ملف README.md بالمحتوى المذكور أعلاه:
     ```bash
     echo "# Setup Environment Role

     This role installs necessary packages for the application environment.

     ## Requirements

     - Ansible 2.9+

     ## Role Variables

     - None

     ## Dependencies

     - None

     ## Example Playbook

     \`\`\`yaml
     - hosts: webservers
       become: yes
       roles:
         - setup_environment
     \`\`\`

     ## License

     MIT

     ## Author Information

     Your Name (or your company)" > README.md
     ```

3. **ملف `deploy_application/README.md`**:
   - انتقل إلى مجلد `deploy_application`:
     ```bash
     cd deploy_application
     ```
   - إنشاء ملف README.md بالمحتوى المذكور أعلاه:
     ```bash
     echo "# Deploy Application Role

     This role deploys the sample application.

     ## Requirements

     - Ansible 2.9+
     - Python 3.x
     - Git

     ## Role Variables

     - app_dir: Directory where the application will be deployed (default: /opt/hello-world-app)

     ## Dependencies

     - None

     ## Example Playbook

     \`\`\`yaml
     - hosts: webservers
       become: yes
       vars:
         app_dir: /opt/hello-world-app
       roles:
         - deploy_application
     \`\`\`

     ## License

     MIT

     ## Author Information

     Your Name (or your company)" > README.md
     ``
