SD Card Setup
=============


1. Find the disk you wish to 

    >> diskutil list

    Sample output::

    /dev/disk0
       #:                       TYPE NAME                    SIZE       IDENTIFIER
       0:      GUID_partition_scheme                        *500.3 GB   disk0
       1:                        EFI EFI                     209.7 MB   disk0s1
       2:          Apple_CoreStorage                         499.4 GB   disk0s2
       3:                 Apple_Boot Recovery HD             650.0 MB   disk0s3
    /dev/disk1
       #:                       TYPE NAME                    SIZE       IDENTIFIER
       0:                  Apple_HFS Macintosh HD           *499.1 GB   disk1
                                     Logical Volume on disk0s2
                                     F3BC43E2-805E-48F9-A23F-5ACFDAF1DC25
                                     Unlocked Encrypted
    /dev/disk2
       #:                       TYPE NAME                    SIZE       IDENTIFIER
       0:      GUID_partition_scheme                        *67.1 GB    disk2
       1:                        EFI NO_NAME                 819.2 KB   disk2s1
       2: 83BD6B9D-7F41-11DC-BE0B-001560B84F0F               16.4 KB    disk2s2
       3:                FreeBSD UFS                         732.4 MB   disk2s3
       4:               FreeBSD Swap                         1.0 MB     disk2s4


2. Unmount the partition

    >> diskutil unmountDisk /dev/disk{NUMBER FROM STEP 1}


3. Write the image to the disk

    >> sudo dd bs=1m if={PATH TO IMG} of=/dev/{NUMBER FROM STEP 1}
