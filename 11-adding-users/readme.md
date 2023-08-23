## Adding users

Create simon user
```
    - name: create simone user
      tags: always
      user: 
        name: simone
        group: root
```

```
ansible-playbook --ask-become-pass site.yml
```

Add authorized_key for that user **authorized_key** module.

Add sudoers file for simone, thanks to that simone will be able to run sudo command without password

## Remove become pass command

Edit ansible.cfg file and add remote_usr with sudo privilliges

```
ansible-playbook site.yml
```

## Bootstrap

Now, we got a problem what do first. At first, we don't have simone user on that server, so we can't at first run those playbook without typing password. So for that we create bootstrap playbook and inside that will be commands which required initiall setup server with users and another thinks which needed ansible itself provision.

Create bootstrap.yml

Add there also lines *changes_when* which keeps outbut a little bit cleaner.

Setup environemt
```
ansible-playbook --ask-become-pass bootstrap.yml
```
After that run another playbook
```
ansible-playbook site.yml
```