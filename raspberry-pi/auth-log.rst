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


sudo cat /var/log/auth.log | grep -i sshd.\*reverse | awk '{ gsub("[\[\]]", "", $12); print $12}' | sort -n |  uniq -c | sort -n | awk '{if ($1 >= 4) print $1,$2 }'


sudo cat /var/log/auth.log | grep -i sshd.\*failed\ password | awk '{print $13}' | sort -n |  uniq -c | sort -n | awk '{if ($1 >= 7) print $1,$2 }'

SSHD Failed Password Attempts
-----------------------------
We can search the auth.log file for connection attempts that resulted in
failures. These can be legitimate failures from you but they are mostly
from your dearly belowed 


The following line will filter out entiries in auth.log which resulted

    >> sudo cat /var/log/auth.log | grep -i sshd.\*failed\ password

Which should return something like this::

    Jul  9 18:26:46 machine sshd[24385]: Failed password for invalid user 1502 from 185.8.148.101 port 53255 ssh2
    Jul  9 18:32:12 machine sshd[24389]: Failed password for invalid user xd from 212.232.52.13 port 57388 ssh2
    Jul  9 18:32:19 machine sshd[24396]: Failed password for invalid user admin from 2.229.82.199 port 54330 ssh2
    Jul  9 18:32:24 machine sshd[24400]: Failed password for invalid user admin from 2.229.82.199 port 54395 ssh2
    Jul  9 18:32:30 machine sshd[24404]: Failed password for invalid user admin from 2.229.82.199 port 54456 ssh2
    Jul  9 18:32:35 machine sshd[24408]: Failed password for invalid user ubnt from 2.229.82.199 port 54515 ssh2
    Jul  9 18:34:04 machine sshd[24417]: Failed password for invalid user 11111 from 79.39.151.124 port 57717 ssh2
    Jul  9 18:35:34 machine sshd[24421]: Failed password for invalid user ADSL from 177.33.142.153 port 56722 ssh2
    Jul  9 18:35:38 machine sshd[24425]: Failed password for invalid user ZXDSL from 178.132.38.67 port 57634 ssh2
    Jul  9 18:44:22 machine sshd[24435]: Failed password for invalid user HPN from 82.105.5.125 port 9770 ssh2
    Jul  9 20:21:34 machine sshd[24464]: Failed password for invalid user admin from 195.154.53.81 port 52106 ssh2
    Jul  9 20:21:40 machine sshd[24468]: Failed password for invalid user support from 195.154.53.81 port 52361 ssh2
    Jul  9 20:21:45 machine sshd[24472]: Failed password for invalid user ubnt from 195.154.53.81 port 52547 ssh2
    Jul  9 20:21:49 machine sshd[24476]: Failed password for invalid user root from 195.154.53.81 port 52712 ssh2


We can further find the top offenders by (you can modify the bit about `>= 7`
to tailor to your specific threshold) summing up each IP address appearance count
and the ::

    >> sudo cat /var/log/auth.log | grep -i sshd.\*failed\ password | awk '{print $13}' | sort -n |  uniq -c | sort -n | awk '{if ($1 >= 7) print $1,$2 }'


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