## Managing services

### Web servers
Manage CentOS servers, to be working automatically after install

Adding task start httpd with *service* module, which provide start service if it is not started. It also got *enabled*, yes property, to make sure if service will be enabled. 

```
ansible-playbook --ask-become-pass site.yml
```

### Restart service

Change index.html file using regexp (it probably could be use in better way). Register it as apache2 name.
Then new task only be started if registered task was changed.
