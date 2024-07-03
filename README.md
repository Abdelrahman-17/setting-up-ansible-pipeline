
1. **ملف `setup_environment/README.md`**:
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

2. **ملف `deploy_application/README.md`**:
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
