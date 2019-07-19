# Ansible
Ansible demo project that will configure a simple web page behind a load balancer and configure Docker for Amazon Linux and Ubuntu EC2 instances.

# Configuration files
./hosts-dev             - Ansible Inventory file containg hosts you want to configure with Ansible

./ansible.cfg           - Ansible Config file with user and ssh key information.

./secrets.yml           - Ignored by .gitignore by default.  You will need to generate a secrets.yml with a "secret_password" variable using    ansible-vault in order for ./playbooks/setup_app.yml to run without error.

# Example Playbooks

Configure Apache behind a load balancer using Ansible Roles.

  ansible-playbook ./setup_role.yml

Perform a Yum Update on 'web' and 'lb' hosts.

    ansible-playbook ./playbooks/yum_update.yml

Install web, lb, and Docker services

    ansible-playbook ./playbooks/install_services.yml

Configure web server.

    ansible-playbook ./playbooks/setup_app.yml

Configure load balancers.

    ansible-playbook ./playbooks/setup_lb.yml

Check Apache service status.

    ansible-playbook ./playbooks/check_status.yml
