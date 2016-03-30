## Local YUM repository Ansible playbook

This playbook will create a local YUM repository and serve the files via HTTP(S) using nginx.

You will need to edit `inventory/local.yml` to match your environment and then run the playbook with the following command.
```
ansible-playbook mirror.yml -i inventory/local.yml 
```
