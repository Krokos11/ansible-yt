## Playbook

Install apache playbook

```
ansible-playbook --ask-become-pass install_apache.yml
```
Ansible run gathering facts (get information about all servers) in every ansible-playbook command run on target.

Remove apache
```
ansible-playbook --ask-become-pass remove_apache.yml
```