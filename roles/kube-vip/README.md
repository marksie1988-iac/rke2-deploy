# Kube VIP

Kube VIP is used to provide a Virtual IP for the RKE2 Servers, this way
should the master be offline, other nodes can still connect to a different
master via the VIP.

All additional nodes should be added via the VIP.

- Creates a directory on all server nodes for manifests
- Gets Kube VIP tags
- Gets the latest Kube VIP version if "latest" is set as the version
- Copies the Kube VIP manifest file to the manifest folder on the master node
