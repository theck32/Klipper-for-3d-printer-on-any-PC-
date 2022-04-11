# Klipper-for-3d-printer-on-any-PC-
Tutoriel pour installer klipper pour imprimante 3d sur n'importe qu'elle ordinateur Portable ou de Bureau

Téléchager Raspbian pour X86 :
https://downloads.raspberrypi.org/rpd_x86/images/rpd_x86-2021-01-12/2021-01-11-raspios-buster-i386.iso

#1 Installer raspbian pour x86
Quand raspbian est installé ouvré un terminal et ecrire:
sudo raspi-config 
dans le menu raspi-config allez dans #3 (Boot option)
et choisir B2 (Console AutoLogin)
redémarré
Configurer votre Wi-Fi avec sudo raspi-config 

#2 Installer le scripts kiauh:
sudo apt-get install git -y
git clone https://github.com/th33xitus/kiauh.git

#3 Pour pouvoir installer klipperscreen dependance:
sudo apt install libcairo2-dev pkg-config

sudo apt install python-gi-cairo

sudo apt installe libgirespository1.0-dev

#4 Ajouter la ligne:
needs_root_rights=yes  
dans ceci:
sudo nano /etc/X11/Xwrapper.config 
ctrl+O et Enter pour sauvegarder 
ctrl+X pour quitter nano

#5 A la fin d'avoir toute installer de klipperscreen :
sudo apt install xserver-xorg-legacy

#6 Ajouter le curseur de la souris dans Klipperscreen
Aller dans :
/klipper_config/KlipperScreen.conf
sudo nano KlipperScreen.conf
et ajouter cette ligne:
show_cursor: True
