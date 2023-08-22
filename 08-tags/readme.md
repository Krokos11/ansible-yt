## Tags

You can add whatever tags you want. 

Run playbook
```
ansible-playbook --ask-become-pass site.yml
```
Nothing changed it that situation.

Check available tags
```
ansible-playbook --list-tags site.yml
```

Run playbook only for chosen tags
```
ansible-playbook --tags centos --ask-become-pass site.yml
```

Run with more tags
```
ansible-playbook --tags "apache,db" --ask-become-pass site.yml
```