CPU Information
===============


Current Clock Speed
-------------------


    >> cat /sys/devices/system/cpu/cpu0/cpufreq/scaling_max_freq

Output::
    
    900000


CPU Temperature
---------------

The Raspberry Pi is built from commercial chips which are qualified to
different temperature ranges; the LAN9512 is specified by the manufacturers
being qualified from 0°C to 70°C, while the AP is qualified from -40°C to 85°C.
You may well find that the board will work outside those temperatures, but 
we’re not qualifying the board itself to these extremes. 

You can get the CPU temperatur from the raspberry pi by executing the following
shell command::

    >> sudo /opt/vc/bin/vcgencmd measure_temp

Which should output::

    >>temp=55.1'C