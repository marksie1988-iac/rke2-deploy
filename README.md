# RKE2-Deploy

This is an ansible playbook that is able to deploy and configure an RKE2 Kubernetes cluster.

Using the calico CNI by default and the ability to use BGP.

BGP exposes the pod IP Addresses so that there is no need for MetalLB and
means that there is no use of your internal IPs for NAT.
