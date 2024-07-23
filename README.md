# RKE2-Deploy

This is an ansible playbook that is able to deploy and configure an RKE2 Kubernetes cluster.

Using the calico CNI which gives the ability to use BGP.

BGP exposes the pod IP Addresses so that there is no need for MetalLB and
means that there is no use of your internal IPs for NAT.

```bash
ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook -u simone --private-key ~/.ssh/id_ed25519 -e 'pub_key="~/.ssh/id_ed25519.pub"' --ssh-extra-args '-o UserKnownHostsFile=/dev/null' main.yaml
```

## Variables

```yaml
vip: 172.16.20.100
bgp_enabled: true
as_number: 64512
router_peer_ip: 172.16.20.1
ansible_become: true
ansible_become_method: sudo
################################################################################
# options to change default values
# kube_vip_version: "latest"
# vip_interface: "eth0"
# rke2_version: "latest"
# rke2_install_dir: "/usr/local/bin"
# cni: calico
# peerIP: 172.16.20.1
# asNumber: 64512
# bgp_enabled: true

```
