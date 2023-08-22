## Command than need sudo
Create non root user on target machine, to compare with root in another
```
ssh krokos@192.168.1.8
sudo adduser krokos
```
Add users to sudogroup
```
su root
usermod -aG sudo krokos
```

Check apt module, which need sudo
```
ansible all -m apt -a update_cache=true
```
It failed.

## Add extra options 

**become** - elevate the privileges by sudo
**ask-become-pass** - ask for become password
```
ansible all -m apt -a update_cache=true --become --ask-become-pass
```
It need the same sudo password for *all* users we connect at once.

## Install actual package
Install vim-nox on all targets
```
ansible all -m apt -a name=vim-nox --become --ask-become-pass
```
Install snapd
```
ansible all -m apt -a name=snapd --become --ask-become-pass
```
Add more arguments
```
ansible all -m apt -a "name=snapd state=latest" --become --ask-become-pass
```

Install all updated
```
ansible all -m apt -a "upgrade=dist" --become --ask-become-pass
```