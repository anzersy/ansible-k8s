# ansible-kubernetes

Use ansible to install kubernetes cluster platfrom.

![arch](./img/arch.png)

## Setup
* Setup ansible(2.4+ advised) and ssh configuration.
* Update inventories to meet your requirement of deployment regarding to various ENV.
* Generate CA key and cert: ```ansible-playbook -i */hosts 01gen_ca.yml.```
* Initialize hosts(cfssl, CA certs, firewalld, selinux, sysctl): ``` ansible-playbook -i */hosts 02init.yml```.
* Setup etcd cluster: ```ansible-playbook -i */hosts 03etcd.yml```.
* Setup kube-master cluster: ```ansible-playbook -i */hosts 04kube-master.yml```.
* Install kubctl: ```ansible-playbook -i */hosts 05kubectl.yml```.
* Install docker: ```ansible-playbook -i */hosts 06docker.yml```.
* Setup kube-node cluster: ```ansible-playbook -i */hosts 07kube-node.yml```.
* Setup calico network: ```ansible-playbook -i */hosts 08calico.yml```.
* Setup dns service in kube: ```ansible-playbook -i */hosts 09dns.yml```.
* Setup dashboard(UI) for kube: ```ansible-playbook -i */hosts 10dashboard.yml```.
* Setup nginx ingress: ```ansible-playbook -i */hosts 11nginx-ingress.yml```.

## Components List
* Kube Master: multi apiserver, scheduler cluster, controller manager cluster
* Kube Node: kubelet, kube-proxy
* Kube Storage: etcd cluster
* Security: enable SSL/TLS
* CRI: docker
* CNI: calico
* Ingress: Nginx
* DNS: kubeDNS, dnsmasq
* UI: dashboard
* CLI: kubectl
* Logger: *(to do)
* Monitor: *(to do)
* Alerter: *(to do)
* CVI: *
* Registry: Harbor(to do)

## Binaries download url list 
* Kube: https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG-1.9.md#downloads-for-v191
* Docker: https://github.com/moby/moby/releases/tag/v1.12.3
* Calicoctl: https://github.com/projectcalico/calicoctl/releases
* CNI: https://github.com/containernetworking/cni/releases
* CFSSL: https://pkg.cfssl.org/

## Images list
* calico/node:v2.6.5
* calico/cni:v1.11.2
* calico/kube-controllers:v1.0.2
* ibmcom/defaultbackend:1.2
* ibmcom/k8s-dns-kube-dns:1.14.1
* ibmcom/k8s-dns-dnsmasq-nanny:1.14.1
* ibmcom/k8s-dns-sidecar:1.14.1
* quay.io/kubernetes-ingress-controller/nginx-ingress-controller:0.9.0
* k8scn/kubernetes-dashboard-amd64:v1.8.0
* anzersy/pause-amd64:3.0

## Helpful links
* https://cfssl.org/
* http://docs.ansible.com/
* https://kubernetes.io/docs/home/
* https://docs.projectcalico.org/v3.0/introduction/

