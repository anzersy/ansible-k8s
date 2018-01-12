# ansible-kubernetes

A role which installs and manages a clustered kubernetes on CentOS 7

## Note

* Ansible 2.4+
* Disable firewall or manage the policy to allow kubernetes's interactivity

## Guide

* Update inventories
* Run command
```    
   ansible-playbook -i inventories/dev/hosts deploy-k8s.yml
```
## Link
https://github.com/anzersy/contrib/tree/master/ansible

