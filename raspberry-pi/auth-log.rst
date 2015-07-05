Inspectign Auth.log
===================
Perhaps one of the useful areas to look into how your SSH service is running
is by insecting the auth log. 


Finding Failures
----------------
You can cat/tail/less/more or whatever command you prefer to inspect the auth
log for failures. The following line will grep (and granted this isn't the
best regex in the world) for most of the failed password attempts that the
SSH daemon encounters::

    >> sudo cat /var/log/auth.log | grep -i sshd.\*failed


Finding top offenders
---------------------
Again you may chose to do which ever utility to parse the log file (in this
excample I've used cat) but the main goal is to parse the whole log, extract
just IP addresses of failed attempts and sort them by their frequencies::

    >> sudo cat /var/log/auth.log | grep -i sshd.\*failed | awk '{print $13}'
        | sort -n |  uniq -c | sort -n

