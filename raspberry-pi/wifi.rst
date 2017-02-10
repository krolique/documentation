USB wifi
========
Contains instructions for dealing with WIFI and other related nonsense.


Setting up WIFI via command line
--------------------------------
Setting up WIFI via command line and other mythical stories. Basically
the current `raspbian` distro comes with `wpa_supplicant`. In order for
this service (daemon) to connect to a local network you'll have to do
a bit of work. 

First edit the configuration file (there might be other stuff writen in the
file, you can just ignore it and append to at the botttom.)::

    > vi /etc/wpa_supplicant/wpa_supplicant.conf

adding the following lines::

    network={
        ssid="The_ESSID_from_earlier"
        psk="Your_wifi_password"
    }

Second, restart the service::

    > sudo ifdown wlan0
    > sudo ifup wlan0
