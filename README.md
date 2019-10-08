**Interface graphique utilisateur pour véhicule robotique fonctionnant sous RaspberryPi **
  ```
  Testé avec Ubuntu 18.04LTS.
  Écrit en python3 avec les librairies Tk and pygame.
  ```
  
**Installation**

Étape 1 - Configuration du répertoire local

Créer un répertoire /rover et attribuer sa propriété à votre utilisateur.

  ```
  sudo -s 
  cd /
  mkdir /rover
  chown <your user>:<your group> /rover
  exit
  ```

Étape 2 - Dans le répertoire /rover, cloner ce repo.

  ```git clone https://github.com/framboiserobot/clientcontrol```
  
Vous devriez avoir ces fichiers:
  ```
  Control.desktop
  README.md
  rover_client_GUI.py
  rover.conf
  ```
  
Étape 3 - Configurer les permissions pour l'exécution.

  ```
  > cd ./clientcontrol
  > chmod +x rover_client_GUI.py
  ```

Étape 4 - Installes les programmes et librairies requises.

mplayer video software
  ```apt-get install -y mplayer```

Librairie Tkinter
  ```apt-get install -y python3-tk```

Gestionnaire de pacquets python3pip
  ```apt-get install -y python3-pip```

La dernière version de la librairie pygame
  ```pip3 install pygame```

La dernière version de la librairie tendo
  ```pip3 install tendo```
  
Étape 5 - Configurer pour l'accès réseau. 

In file rover.conf, set variable ROVER_IP with the IP address used by the Raspberry Pi controler.
  ```
  ROVER_IP = <Ipv4 address>
  ex: ROVER_IP = 192.168.99.1
  ```
  
Étape 6 - Create a desktop shorcut

Move file ```Control.desktop``` to your deskop. The operating system will create a graphic shortcut using this file.
Click [mark executable] when prompted at the initial execution.

  Control.desktop file content:
  
  ```
  [Desktop Entry]
  Version=1.0
  Type=Application
  Name=Control
  Comment=
  Exec=/rover/clientcontrol/rover_client_GUI.py
  Icon=transmission
  Path=/rover/clientcontrol/
  Terminal=false
  StartupNotify=false

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

```
System log window               System command output
Control log - joystick          PS2 controler values     
Control log - motor telemetry   Motor remote telemetry
Video log - video data status   Video bytes received 
```
Video notes
```
The mplayer video program will start when at least 1M of data is received.
Mplayer may freeze (mplayer bug) if you click multiple time on the video screen. 
A complete restart of the GUI might be necessary to correct this. 

If you stop and restart the video module, wait at least 2-3 seconds to allow
the video server to reset and restart, otherwise you will get an error 
message
```
