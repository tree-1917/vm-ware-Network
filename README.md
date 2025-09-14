# vm-ware-Network
how to slove vmnet issue after build vmware

> Slove The issue 

1. Build it and install to kernel modules 
2. ``grep vmnet /proc/devices``
3. create new nodes manually : 
    ```bash
        sudo mknod /dev/vmnet0 c 119 0
        sudo mknod /dev/vmnet1 c 119 1
        sudo mknod /dev/vmnet8 c 119 8
        sudo chmod 666 /dev/vmnet*
    ```
4. restart vmware networking 
    ```bash
        sudo vmware-networks --stop
        sudo vmware-networks --start
    ```
5. Verify 
    ```
        ls -l /dev/vmnet*
    ```