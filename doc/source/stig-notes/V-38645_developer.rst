**Exception**

Changing umask settings can disrupt some systems and this change requires a
deployer to opt-in. To opt-in for this change and adjust the umask, set the
following Ansible variable:

.. code-block:: yaml

    security_umask_login_defs: 077
