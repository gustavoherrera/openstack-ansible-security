**Exception**

Although a minimal set of iptables rules are configured on openstack-ansible
hosts, the "deny all" requirement of the STIG is not met. This is largely left
up to the deployer to do, based on their assessment of their own network
segmentation.

Deployers are urged to review the network access controls that are applied
on the network devices between their OpenStack environment and the rest of
their network.
