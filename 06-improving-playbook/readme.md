## Cleanup playbook

Install package in one task, using list of packages. Then run

```
ansible-playbook --ask-become-pass install_apache.yml
```

It is use variables and **package** module which allow to use generall package installation on different Linux distributions.