**Exception and opt-in alternative**

Adjusting PAM configurations is very risky since it affects how all users
authenticate. In addition, ``pam_faillock.so`` isn't available in Ubuntu.

Another option is to utilize ``pam_tally`` to deny logins after failed
attempts. Adjusting PAM configurations automatically can disrupt the operation
of production systems, so this is left up to the deployer to configure.
For more details on how to configure ``pam_tally``, refer to `this AskUbuntu
article about pam_tally`_.

Another alternative is `fail2ban`_. Read the notes below for more tails on
this option.

The Ansible tasks will install `fail2ban`_ and configure it to ban IP
addresses using the following logic

* The IP has attempted three logins in the last 10 minutes and all have failed
* That IP will be banned for 15 minutes (via iptables rules)

Deployers must opt-in for fail2ban to be installed and configured. To opt-in,
set the ``security_install_fail2ban`` Ansible variable to ``yes``. The time
period for bans can also be configured (in seconds) via tha
``security_fail2ban_bantime`` variable:

.. code-block:: yaml

    security_install_fail2ban: yes
    security_fail2ban_bantime: 900

**NOTE:** Fail2ban can only review authentication attempts for services that
listen on the network, such as ssh. It has no control over physical consoles.
Deployers are strongly urged to use stong physical security policies to
prevent unauthorized users from accessing server consoles. In addition,
deployers must secure out-of-band access methods, like IPMI, as they can be
vectors for physical console access as well.

.. _this AskUbuntu article about pam_tally: http://askubuntu.com/questions/59459/how-do-i-enable-account-lockout-using-pam-tally
.. _fail2ban: https://en.wikipedia.org/wiki/Fail2ban
