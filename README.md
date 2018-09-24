# Opticam IP Camera Viewer with Raspberry Pi

1. Download the latest Raspbian Noob image from [Raspberry Pi Website](https://www.raspberrypi.org/downloads/raspbian/)
2. Download [win32diskimager](https://sourceforge.net/projects/win32diskimager/)
3. After writing the image to the SD card and booting up the Raspberry Pi, go to terminal window
4. Once in terminal window enter Raspberry Pi config by typing

    ```shell
    sudo raspi-config
    ```
    
5. Select following options:

    ```shell
    3) Boot Options 
        > Wait For Network at Boot
    4) Localisation Options 
        > Change Timezone 
           > (select appropriate timezone)
    5) Interfacing Options 
        > SSH 
           > Yes
    7) Advanced Options
        > Expand File System
        > Memory Split
           > 256
    ```
    
6. Enable autologin and change booting to CLI
7. Boot into console and update your Raspberry Pi by running following command

    ```shell
    sudo apt-get update && sudo apt-get upgrade -y && sudo reboot
    ```
    
8. Assign a static IP address by editing the `/etc/dhcpcd.conf` file and reboot the computer

    ```shell
    interface eth0
    static ip_address=192.168.1.200  # enter your ip here
    static routers=192.168.1.1
    static domain_name_servers=192.168.1.1 8.8.8.8
    ```
    
