**Client GUI for RaspberryPi robotic vehicle control system**
  ```
  Tested OK on Ubuntu 18.04LTS.
  Written in python3 with the help of Tk and pygame libraries.
  ```
  
**Installation**

Step 1 - In your home directory, clone this repo.

  > git clone https://github.com/framboiserobot/clientcontrol
  
You should have these files:
  ```
  README.md
  rover_client_GUI.py
  rover.conf
  ```
  
Step 2 - Set permissions for execution.

  > cd ./clientcontrol
  > chmod +x rover_client_GUI.py

Step 3 - Install required libraries.

mplayer video software
  > apt-get install mplayer

Tkinter library
  > sudo apt-get install python3-tk 

Python3 package manager
  > apt-get install -y python3-pip

Latest version of pygame
  > pip3 install pygame

Latest version of tendo
  > pip3 install tendo
  
Step 4 - Configure for network access. 

In file rover.conf, set variable ROVER_IP with the IP address used by the Raspberry Pi controler.
  ```
  ROVER_IP = <Ipv4 address>
  ex: ROVER_IP = 192.168.99.1
  ```
  
**Basic Usage**

Buttons 
```
[start]         Start all user interface modules 
[stop]          Stop all user interface modules
[Ping rover]    Send ICMP request to RaspberryPi vehicle control instance
[Reboot]        Reboot RaspberryPi vehicle control instance
[Shutdown]      Shutdown RaspberryPi vehicle control instance
[Start control] Start user interface control module only
[Stop control]  Stop user interface control module only
[Start video]   Start user interface video module only
[Stop video]    Stop user interface video module only
[Exit]          Exit user interface program
```
Log windows

4 log windows are available


