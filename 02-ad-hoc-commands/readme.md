## Update ansible 
Add inventory file
```
root@192.168.1.8
root@192.168.1.16
```

Command to check connection and everything is working
```
ansible all --key-file ~/.ssh/ansible -i inventory -m ping
```

## Ansible config file

Create file **ansible.cfg**. 
This file is run by ansible, whenever you run it. Local **ansible.cfg** file override that, which is located globally in **/etc/ansible**.

Now we can write previous ping command shorter
```
ansible all -m ping
```

## Commands

### Show all hosts
```
ansible all --list-hosts
```
### List of detailed information
About all target servers
```
ansible all -m gather_facts
```
Only for one host
```
ansible all -m gather_facts --limit root@192.168.1.8
```



