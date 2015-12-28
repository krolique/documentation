SD Card Setup
=============
This section deals with writing the .img files to the SD Cards on the raspberry
pi using the command line


1. Find the disk you wish to::

    >> diskutil list

        /dev/disk1
           #:                       TYPE NAME                    SIZE       IDENTIFIER
           0:                  Apple_HFS Macintosh HD           *499.1 GB   disk1
        /dev/disk2
           #:                       TYPE NAME                    SIZE       IDENTIFIER
           0:      GUID_partition_scheme                        *67.1 GB    disk2

2. Unmount the partition::

    >> diskutil unmountDisk /dev/disk{NUMBER FROM STEP 1}


3. Write the image to the disk::

    >> sudo dd bs=1m if={PATH TO IMG} of=/dev/{NUMBER FROM STEP 1}
