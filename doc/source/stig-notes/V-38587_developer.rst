The ``telnetd`` service will be removed by the Ansible tasks, if it is
installed.  To opt-out of this change, adjust the following variable
to ``no``:

.. code-block:: yaml

    security_remove_telnet_server: no
