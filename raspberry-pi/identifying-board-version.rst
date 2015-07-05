Identifying board version
=========================
Identifying the board version is easy by inspecting the output from
`/proc/cpuinfo` and matching the 'Revision' field value to the table below


+------------------------+--------+----------------------------+
| Model and Pi Revision  | Memory | Revision Code from cpuinfo |
+------------------------+--------+----------------------------+
| Model B Revision 1.0   | 256 MB | 0002                       |
+------------------------+--------+----------------------------+
| Model B Revision 1.0   | 256 MB | 0003                       |
| +ECN0001 (no fuses,    |        |                            |
| D14 removed)           |        |                            |
+------------------------+--------+----------------------------+
| Model B Revision 2.0   | 256 MB | 0004, 0005, 0006           |
| Mounting holes         |        |                            |
+------------------------+--------+----------------------------+
| Model A Mounting holes | 256 MB | 0007, 0008, 0009           |
+------------------------+--------+----------------------------+
| Model B Revision 2.0   | 512 MB | 000d, 000e, 000f           |
| Mounting holes         |        |                            |
+------------------------+--------+----------------------------+
| Model B+               | 512 MB | 0010                       |
+------------------------+--------+----------------------------+
| Compute Module         | 512 MB | 0011                       |
+------------------------+--------+----------------------------+
| Model A+               | 256 MB | 0012                       |
+------------------------+--------+----------------------------+
| Pi 2 Model B           | 1 GB   | a01041 (Sony, UK) a21041   |
|                        |        | (Embest, China)            |
+------------------------+--------+----------------------------+

Example output from 'cpuinfo'::

    processor   : 0
    model name  : ARMv6-compatible processor rev 7 (v6l)
    BogoMIPS    : 2.00
    Features    : half thumb fastmult vfp edsp java tls 
    CPU implementer : 0x41
    CPU architecture: 7
    CPU variant : 0x0
    CPU part    : 0xb76
    CPU revision    : 7

    Hardware    : BCM2708
    Revision    : 000e
    Serial      : 00000000528e1136






    