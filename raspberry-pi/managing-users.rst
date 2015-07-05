Managing Users
==============
You should always remove the pi user from the system and create a new user
with a unique name on the box.

1.  Create a new user account to use::

        >> sudo adduser {NAME}

2.  Enable sudo access but editing the `/etc/sudoers` file::

        >> sudo vim /etc/sudoers

    Remove the pi from sudoers and add the new account::

        >> {NAME} ALL=(ALL) NOPASSWD: ALL

3. Remove the use pi from the system and delete the home dir::

    >> sudo deluser pi
    >> sudo rm -rf /home/pi
