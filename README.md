# automount-USB-drive-on-Raspberry-Pi

## Step 01:
Install [latest Raspbian](https://www.raspberrypi.org/downloads/) Stretch on RPI
				
## Step 02:
Run the following commands to update installed packages:
  
    $ sudo apt-get update
    $ sudo apt-get upgrade
		
## Step 03:
Expand your root partition:
  
	$ sudo raspi-config
	Select option: "1 Expand Filesystem"
			
## Step 04:
- Make sure USB Disks are formatted as fat32.
- In order to mount your USB drive permanently to a specified path add the following line into your /etc/fstab config file:

		/dev/sda1       /media/pi/USB1           vfat    defaults        0       0
      
- You need sudo permissions to edit this file so the right format to edit this file is as follows:

		$ sudo nano /etc/fstab
      
- Add the line above and hit `ctrl+o -> Enter ->ctrl+x`. This will save the file and then exit
		
## Step 05: 

Please confirm that pendrive is actually mounted to your specified path. For this:
  
	$ sudo lsblk
    
The above command will return a list of devices and their mount points 
	
-------------------------------------------------------Hope this helps-----------------------------------------------------------  
`P.S.` Note that with raspbian strectch all pendrives/usbdrives are assigned `/dev/sda1` label. However, the above mount line may fail:

If you add or remove additional drives from your Linux system so you are advised to connect only 1 USB drive with RPI at a time
