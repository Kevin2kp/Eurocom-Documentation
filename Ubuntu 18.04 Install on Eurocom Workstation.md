# Ubuntu 18.04 Installation on Eurocom Workstation 

This guide will walk you through installing Ubuntu 18.04 on a Eurocom workstation. To follow this guide you will need:

* Ethernet connection
* USB stick with at least 1 GB of space
* Working computer from which to create a liveUSB 

## Create live USB

1. Download the Ubuntu Server ISO from the official Ubuntu downloads page. For this installation we will use the [Alternate Ubuntu Server installer](https://www.ubuntu.com/download/alternative-downloads#alternate-ubuntu-server-installer).

2. Create a live USB from the Ubuntu Server ISO.
	* Instructions for [Windows](https://tutorials.ubuntu.com/tutorial/tutorial-create-a-usb-stick-on-windows#0)
	* Instructions for [macOS](https://tutorials.ubuntu.com/tutorial/tutorial-create-a-usb-stick-on-macos#0)
	* Instructions for [Ubuntu](https://tutorials.ubuntu.com/tutorial/tutorial-create-a-usb-stick-on-ubuntu#0)

## Change BIOS settings

*  Disable **secure boot** 
*  Set boot mode to **UEFI**, and disable **CSM**
*  Set SATA mode to **AHCI**

## Install Ubuntu Server

1. Plug in the Ethernet cable to the laptop. The installer should automatically set up the network connection once it is loaded.
2. Boot from the liveUSB and proceed with the installation until the partition step. At this point, if you would like to set up software RAID, follow these instructions.
3. Complete the installation and reboot

## Install packages

1. Login using the credentials made during the installation.
2. The following packages can be installed in any order:

   * **Official Nvidia drivers**
   To install the official drivers add the official *Proprietary GPU Drivers* repository by running:
		~~~
		sudo add-apt-repository ppa:graphics-drivers/ppa
		~~~
		Then install the latest driver. In this case, the latest driver is 418:
		~~~
		sudo apt install nvidia-driver-418
		~~~
		 

   * **Keyboard back-light controller (optional)**
   Clone the # **[tuxedo-keyboard](https://github.com/tuxedocomputers/tuxedo-keyboard)** git repository by running:
      ~~~
	  git clone https://github.com/tuxedocomputers/tuxedo-keyboard.git
	  ~~~
       Then follow the instructions in the repository.
       
    *  **Ubuntu Desktop**
     This will install a GUI and an assortment of applications. To install run:
	     ~~~
	     sudo apt install ubuntu-desktop
	     ~~~
Once all packages are installed, reboot the computer. At this point you should have a working installation of Ubuntu.


	     
