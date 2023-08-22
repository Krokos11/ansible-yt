## Conditional

### When conditional

If is only one condition, we can use *==*
```
  - name: install apache2 package
    apt:
      name: apache2
      state: latest
    when: ansible_distribution == "Ubuntu"
```

For more conditions, we can use *in* and table on conditions
```
  - name: install apache2 package
    apt:
      name: apache2
      state: latest
    when: ansible_distribution in ["Debian", "Ubuntu"]
```
### Get env from targets
```
ansible all -m gather_facts
or
ansible all -m gather_facts --limit krokos@192.168.1.8
```
Get distribution
```
ansible all -m gather_facts --limit krokos@192.168.1.8 | grep ansible_distribution
```

### Fit for CentOS distribution
Copy all tasks and change *when* condition and module from **apt** to **dnf** and some names of packages.
