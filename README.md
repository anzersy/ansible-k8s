# ansible-etcd3

A role which installs and manages a clustered etcd 3.x on CentOS 7

## Note

* Ansible 2.4+
* Disable firewall or manage the policy to allow etcd's interactivity

## Guide

* Update inventories
* Run command
```    
   ansible-playbook -i inventories/dev/hosts deploy-etcd3.yml
```
## Link
https://github.com/anzersy/contrib/tree/master/ansible

