## Target specific host

Create new Ubuntu lxc.
Update Inventory files with groups.

```
ansible-playbook --ask-become-pass site.yml
```

### Pres tasks

*pre_tasks* instead of *tasks* if we want to run those tasks before