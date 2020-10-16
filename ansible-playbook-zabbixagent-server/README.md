# Ansible playbook to change your zabbix agent's Server and Server Active IP
ansible-playbook. Add and configure zabbix-agent.

Run with: ansible-playbook zabbix-agent.yml -u YOUR_USER --ask-pass --extra-vars='ansible_become_pass=YOUR_SUDO_PASS'

This playbook is meant to change Server and ServerActive IPs from your zabbix_agentd.conf

You have to modify these 2 files:
1)zabbix-agent.yml --- "remote_user" and "hosts"
2)roles/zabbix.agent/tasks/main.yml --- "line: 'ServerActive=XXX.XXX.XXX.XXX'" and "line: 'Server=XXX.XXX.XXX.XXX'" with your server ip-address

#Changelog
Version 0.01
 - It stops your zabbix agent service and starts again after the changes were done.
