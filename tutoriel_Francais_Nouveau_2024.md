--Nouveau,(2024-01-09)--
Tutoriel pour installer klipper pour imprimante 3d sur n'importe qu'elle ordinateur Portable ou de Bureau

Don PayPal: jeromest_gelais@hotmail.com

Téléchager Raspbian pour X86 :
https://downloads.raspberrypi.org/rpd_x86/images/rpd_x86-2022-07-04/2022-07-01-raspios-bullseye-i386.iso

Écrire ce .ISO sur une clef usb avec Etcher ou autre!

Démarrer votre ordinateur sur cette clef usb!

#1 Installer raspbian pour x86 
Choisir Install et non Graphics install
Quand raspbian est installé ouvré un terminal et écrire:

sudo raspi-config

dans le menu raspi-config allez dans:

1 (Systems Options)

S5 (Boot option)

B2 (Console AutoLogin

Retourner au début du menu raspi-config

3 (Interfacing Options)

I2 SSH

Choisir Yes dans "Would you like the SSH server to be enabled?"

Allez dans Finish en bas à droite

Configurer votre WIFI dans le haut droite ou le faire dans sudo raspi-config! Quand cela est fait retourner dans le terminal deja ouvert et ecrivé :
sudo reboot

Maintenant vous allez redémarré sur un terminal uniquement vérifier votre connexion internet avec la command : ifconfig

#2
sudo apt-get update && sudo apt-get install git -y

git clone https://github.com/dw-0/kiauh.git

./kiauh/kiauh.sh

update (2)
system (12)
install (1)
Klipper(1)
add user 'pi' to group(s) now? Y
Moonraker(2)
Y
Mainsail(3) ou Fluidd(4) au choix
exemple Fluidd (4)
Download the recommended macros? Y
KlipperScreen (5)

sudo apt-get update

cd KlipperScreen
cd ks_includes
sudo nano defaults.conf
[main]
show_cursor: True
CTRL+O et ENTER (Pour sauvegarder)
CTRL+Xpour quitter nano

sudo nano /etc/X11/Xwrapper.config
Écrire: needs_root_rights=yes 
A la première ligne!
ctrl+O et ENTER pour sauvegarde
ctrl+X  pour quitter nano
sudo reboot
