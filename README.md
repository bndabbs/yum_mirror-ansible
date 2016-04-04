## Local YUM repository Ansible playbook

This playbook will create a local YUM repository and serve the files via HTTP using nginx.

Make sure you have sufficient space to host all of the repo files in `/usr/share/nginx/html/repos/`. I budget for ~50GB with the currently selected repos. I also mount this as a separate volume so I don't corrupt the whole system in the event it does fill up.

You will need to edit `inventory/local.yml` to match your environment and then run the playbook with the following command.
```
ansible-playbook mirror.yml -i inventory/local.yml -b
```

Once the playbook has finished, you can curl a repo file from nginx to enable all the things:

```
cd /etc/yum.repos.d/
curl -O http://nginx_ip/centos/7/local.repo
yum install yum-priorities
```

**Note:** *The provided repo file uses priorities to give the local ones precedence over the online ones.*
