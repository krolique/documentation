CPU Information
===============
Each board contains a CPU (SoC) you can identify each CPU by model in the
following chart

+-------------------------+-----------------------------------+
|          Model          |               CPU                 |
+-------------------------+-----------------------------------+
| Model A                 | 700 MHz single-core ARM1176JZF-S  |
+-------------------------+-----------------------------------+
| Model A+                | 700 MHz single-core ARM1176JZF-S  |
+-------------------------+-----------------------------------+
| Model B                 | 700 MHz single-core ARM1176JZF-S  |
+-------------------------+-----------------------------------+
| Model B+                | 700 MHz single-core ARM1176JZF-S  |
+-------------------------+-----------------------------------+
| Model B (Generation 2)  | 900 MHz quad-core   ARM Cortex-A7 |
+-------------------------+-----------------------------------+


Current Clock Speed
-------------------
You can find the current clock speed of the CPU by running the following
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
    
Operating System
----------------
You can find out more information about the operating system executing
the following linux command::

    >> hostnamectl

which should output something like this::

       Static hostname: maya
             Icon name: computer
               Chassis: n/a
            Machine ID: ...
               Boot ID: ...
      Operating System: Raspbian GNU/Linux 8 (jessie)
                Kernel: Linux 4.1.13-v7+
          Architecture: arm
