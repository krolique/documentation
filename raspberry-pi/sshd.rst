SSDH Configuration
==================

Edit the `/etc/ssh/sshd_config` file and set these value

1.  Set protocol to version 2 only (may not be need as most configuration default
    to this setting already)::

        Protocol 2

2. Disable root login::

    PermitRootLogin no

3. Specify the allowed ssh users::

    AllowUsers user1 user2....

Restart the current service by issuing the following command::

    >> sudo /etc/init.d/ssh restart