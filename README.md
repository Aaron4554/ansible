# Ansible repo for homelab
Primarily just used to run updates on my VMs, LXCs, Pi, and Laptop.

## Notes
To run `ansible-playbook playbook/create_svc_user.yml -u root -k` comment out 'remote_user = rocannon_svc' in ansible.cfg and comment out '[all:vars]' && '[ansible_user=rocannon_svc]'
Make sure the host has 'PermitRootLogin yes' in /etc/ssh/sshd_config. change back to '#PermitRootLogin prohibit-password' after.
To run `ansible-playbook playbook/updates.yml` rocannon_svc need to have NOPASSWD: ALL inside all hosts (handled by setup.yml) or it will not work. ansible.cfg and inventory/hosts can have 'remote user' && '[all:vars]' && '[ansible_user]' commented out.

There is a cron job that runs updates.yml every Sunday at 0300. You can see/edit it with crontab -e. It writes logs to /var/logs/ansible/updates.log
