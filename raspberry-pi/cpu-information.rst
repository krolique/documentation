CPU Information
===============


700 MHz single-core ARM1176JZF-S    
900 MHz quad-core ARM Cortex-A7


Current Clock Speed
-------------------
You can find the maximum clock speed of the CPU by running the following
command::

    >> cat /sys/devices/system/cpu/cpu0/cpufreq/scaling_max_freq

The out put should be something like this::
    
    >> 900000


CPU Temperature
---------------
The raspberry pi CPU processors [chip] are made by a commercial vendors. The 
temperature range for commercially manufactured chips may fall between -40°C 
and 85°C. You can get the CPU temperature from the raspberry pi by executing
the following shell command::

    >> sudo /opt/vc/bin/vcgencmd measure_temp

which should output something like this::

    >> temp=55.1'C