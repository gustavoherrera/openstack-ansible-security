Ubuntu keeps 5 rotated logs with the ``security_num_logs`` option and this
meets the STIG requirement. The Ansible task will ensure that the secure
default is maintained.

Deployers who want to allow logs to grow to larger sizes prior to rotation can
adjust the following Ansible variable:

.. code-block:: yaml

    security_num_logs: 5
