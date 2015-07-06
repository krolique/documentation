Inspecting Auth.log
===================
Perhaps one of the useful areas to look into whose connecting to your machine
via SSH is the `auth.log` found in `/var/log/` (granted this setup may not be
the same for all the UNIX/Linux distributions)

Install Fail2Ban
----------------
The simplest way to slow down ssh login attempts is to install a package called
`Fail2Ban` which is a simple python script that (among other things) blocks
users. Install the package by issuing the following command::

    >> sudo apt-get install fail2ban


Finding Failures
----------------
The following line will grep (and granted this isn't the best reg-ex in the
world) for most of the failed password attempts that the SSHD agent 
encounters::

    >> sudo cat /var/log/auth.log | grep -i sshd.\*failed


Finding Top Offenders
---------------------
You may find it useful to find the number of failed ssh attempt by IP. This
can be achieved by issuing the following command::

    >> sudo cat /var/log/auth.log | grep -i sshd.\*failed | awk '{print $13}'
        | sort -n |  uniq -c | sort -n


Block most frequent offenders
-----------------------------
Block frequent offenders is easy with iptables. The following command block
a single or a range of IPs (permanently)::

    >> sudo /sbin/iptables -I INPUT -s {IP/IP RANGE} -j DROP