The security role will add a file in ``/etc/security/limits.d/`` that disables
core dumps for all users. Although this setting is more secure, it can prevent
users from debugging kernel errors.

To opt-out of this change, set the following Ansible variable to ``no``:

.. code-block:: yaml

    security_disable_core_dumps: no
