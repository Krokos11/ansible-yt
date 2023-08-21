# Generate ssh keys

## Genereate key
```
ssh-keygen -t ed25519 -C "krokos default"
```
**ed25519** - more secure type than default. It is also shorter
**-C** - comment

And setup passphrase

## Copy key to target
```
ssh-copy-id -i ~/.ssh/id_ed25519.pub root@192.168.1.8
```

## Key for ansible
```
ssh-keygen -t ed25519 -C "ansible"
```
Without passphrase

## Copy ansible key
```
ssh-copy-id -i ~/.ssh/ansible.pub root@192.168.1.8
```
## Login using ansible key
```
ssh -i ~/.ssh/ansible root@192.168.1.8
```
## SSH Agent cheat
Thanks to that, it cache passphrase to private key, so you can write password only once.
```
eval $(ssh-agent)
```
Add passphrase to cache
```
ssh-add
```
Now you can login by ssh using ssh-keys with passphrase, without typing passphrase every time.
But it's not pernament. It is only for this terminal session.

For better permormance, we can use alias. We can now use two commands, only using **ssha** command.
```
alias ssha='eval $(ssh-agent) && ssh-add'
```
We can now use two commands, only using **ssha** command.
```
ssha
```
But you close terminal, you lose your alias, so for that edit proper file 
```
nano .bashrc
```
and add line with alias
```
alias ssha='eval $(ssh-agent) && ssh-add'
```

## Login to github using ssh
Thanks to previous moves, you can easily clone github repository using ssh keys. Just add public ssh key to repository and then clone repo using ssh link.
