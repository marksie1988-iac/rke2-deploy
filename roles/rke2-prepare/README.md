# RKE2 Prepare

This role prepares all nodes ready for joining the cluster, it also
builds the first server node.

- Creates directory for RKE2 Config & Token
- Deploys the RKE2 Server config file to the first server
- Creates the server service on all servers
- Creates the agent service on all agents
- Starts rke2-server service on the first server node
- Waits until the token and kubectl are available
- Copies Kubectl to the first server `/usr/local/bin` folder
- Amends the token access to allow reading
- Adds the token to a variable for later use
- Restore token access
- Create the `.kube` config in the `ansible_user` home folder
- Copy config to `.kube` folder
- Replace the IP Address in the config with the VIP IP
