# Klipper-for-3d-printer-on-any-PC-
Tutoriel pour installer klipper pour imprimante 3d sur n'importe qu'elle ordinateur Portable ou de Bureau

Don PayPal: jeromest_gelais@hotmail.com

Téléchager Raspbian pour X86 :
https://downloads.raspberrypi.org/rpd_x86/images/rpd_x86-2021-01-12/2021-01-11-raspios-buster-i386.iso

Écrire ce .ISO sur une clef usb avec Etcher ou autre!

Démarrer votre ordinateur sur cette clef usb!

#1 Installer raspbian pour x86
Quand raspbian est installé ouvré un terminal et ecrire:

sudo raspi-config
 
dans le menu raspi-config allez dans:
 
1 (Systems Options)

S5 (Boot option)

B2 (Console AutoLogin)

Activer le SSH:

Retourner au début du menu raspi-config 

3 (Interfacing Options)

P2 SSH

Choisir Yes dans “Would you like the SSH server to be enabled?”

Allez dans Finish en bas à droite

redémarré

#2 Ecrivez la commande : 

ls /dev/serial/by-id/

Cela vous donnera le lien pour écrire dans [mcu] de printer.cfg

Configurer votre Wi-Fi avec: (Vous pouvez utiliser un câble Ethernet si vous avez pas de wifi)

sudo raspi-config 

1 et S1 (Wireless LAN)

#3 Installer le scripts kiauh:

sudo apt-get install git -y

git clone https://github.com/th33xitus/kiauh.git

Ouvrir kiauh :

cd kiauh

./kiauh.sh

Installer :

Klipper,moonraker,Fluidd et quitter kiauh et installer 
les dépendances pour Klipperscreen le #3 du tuto!

#4 Pour pouvoir installer klipperscreen vous devez installer c'est dépendances:

sudo apt-get update

sudo apt-get upgrade

sudo apt install libcairo2-dev pkg-config

sudo apt install python-gi-cairo

sudo apt install libgirepository1.0-dev

#5 Ouvrer kiauh et installer Klipperscreen 

#6 Ajouter le curseur de la souris dans Klipperscreen:

Aller dans :

klipper_config avec cette commande:

cd ..

cd klipper_config

Ensuite cette commande:

sudo nano KlipperScreen.conf

et ajouter cette ligne:

#~# show_cursor: True

ctrl+O et Enter pour sauvegarder 

ctrl+X et Enter pour quitter nano

#7 Ajouter la ligne (Écrivez la pour qu'elle soit en premier):

needs_root_rights=yes 
 
dans ceci:

sudo nano /etc/X11/Xwrapper.config 

ctrl+O et Enter pour sauvegarder 

ctrl+X et Enter pour quitter nano

#8 A la fin d'avoir toute installer pour klipperscreen : (Pas toujours obligatoire)

sudo apt install xserver-xorg-legacy




voilà klipper,fluidd,moonraker et Klipperscreen 
est maintenant installé et prêt à être utilisé 
avec une souris pour une écran non tactile sur vôtre Imprimante 3D!

Jérôme St-gelais (2022) Don PayPal jeromest_gelais@hotmail.com
