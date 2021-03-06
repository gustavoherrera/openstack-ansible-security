**Exception**

Deployers that use LDAP authentication for systems are strongly urged to use
TLS connectivity between client hosts and LDAP servers to prevent eavesdroppers
on the network from reading the authentication attempts as they are made. The
certificates on the LDAP server must be trusted by each client.

The tasks in the security role do not adjust the LDAP configuration since this
could disrupt future authentication attempts.
