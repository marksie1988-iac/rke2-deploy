# Deploy CNI

This role will deploy a CNI with its required config.

Currently only Calico is supported.

- Checks if `cni` is set to `calico` and that this is the first server

## Calico

- Check if calico tigera operator namespace exists
- Check if the tigera operator pod exists
- If it doesnt, download the calico manifest
- Copy the calico-config template
  - If `bgp_enabled` then it will enable BGP
  - For BGP you need to set:
    - `peerIP` to your router
    - `asNumber` to the router AS Number
- Copy the calico node status manifest
  - This loops through all nodes to create a monitor for each one
- Create a calico directory and copy the calicoctl config
- Download & Install calicoctl
