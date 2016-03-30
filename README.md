## Local YUM repository Ansible playbook

This playbook will create a local YUM repository and serve the files via HTTP(S) using nginx.

Make sure you have sufficient space to host all of the repo files in `/usr/share/nginx/html/repos/`. I budget for ~75GB with the currently selected repos. I also mount this as a separate volume so I don't corrupt the whole system in the event it does fill up.

You will need to edit `inventory/local.yml` to match your environment and then run the playbook with the following command.
```
ansible-playbook mirror.yml -i inventory/local.yml
```
