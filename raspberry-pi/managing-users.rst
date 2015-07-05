Managing Users
==============
The first step would be to remove the `pi` user account from the system.

1. Create a new user account to use::

    >> sudo adduser {NAME}

2. Enable sudo access but editing the `/etc/sudoers` file::

    >> sudo vim /etc/sudoers

and remove the pi from sudoers and add the new account::

    >> {NAME} ALL=(ALL) NOPASSWD: ALL

3. Remove the use pi from the system and delete the home dir::

    >> sudo deluser pi
    >> sudo rm -rf /home/pi


