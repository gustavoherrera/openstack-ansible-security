The Ansible task for V-38462 already checks for configurations that would
disable any GPG checks when installing packages. However, it is possible for
the root user to override these configurations via command line parameters.
