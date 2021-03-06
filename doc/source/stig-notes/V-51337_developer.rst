The tasks in the security role will enable the Linux Security
Module (LSM) that is appropriate for the Linux distribution in use.

For Ubuntu, the default LSM is AppArmor.  Refer to Ubuntu's `AppArmor
documentation`_ for more details on how AppArmor works. The tasks will enable
AppArmor and start it immediately on the system.

For CentOS, the default LSM is SELinux. Refer to Red Hat's `Security-Enhanced
Linux`_ documentation for more details on SELinux. The tasks will enable
SELinux on the next boot.

.. note::

    **If SELinux was disabled before the security role was applied, the
    filesystem will be automatically relabeled on the next boot.** For most
    systems, this process only takes a few minutes. However, it can take
    additional time to finish on systems with slow disks or a large number of
    files.

    Deployers are strongly urged to relabel the filesystem if the system has
    never had SELinux in enforcing mode previously. Rebooting into enforcing
    mode with a partially-labeled filesystem can lead to unnecessary SELinux
    policy denials.

Deployers can opt-out of this change by setting the following Ansible variable:

.. code-block:: yaml

    security_enable_linux_security_module: False

Setting the variable to ``False`` will prevent the tasks from making any
adjustments to the LSM status.

On CentOS 7, the security role will verify that SELinux is in *Enforcing* mode.
If SELinux is in *Disabled* or *Permissive* mode, the playbook will fail with
an error message.

.. _AppArmor documentation: https://help.ubuntu.com/community/AppArmor
.. _Security-Enhanced Linux: https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/6/html/Security-Enhanced_Linux/
