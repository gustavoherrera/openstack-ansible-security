**Exception**

Altering partitions and how they are mounted is left up to the deployer
to configure during the OS installation process.  Mounting ``/tmp/``
with the ``noexec`` option is highly recommended to prevent scripts
or binaries from being executed from ``/tmp``.
