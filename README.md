**Interface graphique utilisateur pour véhicule robotique fonctionnant sous RaspberryPi**
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

Étape 4 - Installer les programmes et librairies requises.

Interface vidéo mplayer
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

Dans le fichier rover.conf, assigner à la variable ROVER_IP l'adresse IP du véhicule robotiqye.
  ```
  ROVER_IP = <Ipv4 address>
  ex: ROVER_IP = 192.168.99.1
  ```
  
Étape 6 - Créer un raccourci sur le bureau 
Déplacer le fichier ```Control.desktop``` sur votre bureau. Le système d'opération va utiliser ce fichier pour créer un raccourci. Cliquez sur le bouton [mark executable] au moment de l'exécution initiale.

  Contenu de Control.desktop:
  
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
 
**Utilisation**

Buttons 
```
[start]         Démarrer tout les modules
[stop]          Arrêter tout les modules
[Ping rover]    Envoyer un Ping au véhicule robotique
[Reboot]        Redémarrer le véhicule robotique
[Shutdown]      Éteindre le véhicule robotique (software shutdown)
[Start control] Démarrer le module de contrôle
[Stop control]  Arrêter le module de contrôle
[Start video]   Démarrer le module video
[Stop video]    Arrêter le module video
[Exit]          Quitter le programme
```
Log windows

4 fenêtres de données sont disponible

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
