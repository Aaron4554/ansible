# Ansible repo for homelab
Primarily just used to run updates on my VMs, LXCs, Pi, and Laptop.

## Notes
To run `ansible-playbook playbook/create_svc_user.yml -u root -k` comment out 'remote_user = rocannon_svc' in ansible.cfg and comment out '[all:vars]' && '[ansible_user=rocannon_svc]'
Make sure the host has 'PermitRootLogin yes' in /etc/ssh/sshd_config. change back to '#PermitRootLogin prohibit-password' after.
