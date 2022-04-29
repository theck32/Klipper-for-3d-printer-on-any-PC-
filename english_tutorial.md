# Klipper-for-3d-printer-on-any-PC-
Tutorial to install klipper for 3d printer on any Laptop or Desktop

Donation PayPal: jeromest_gelais@hotmail.com

Download Raspbian for X86:
https://downloads.raspberrypi.org/rpd_x86/images/rpd_x86-2021-01-12/2021-01-11-raspios-buster-i386.iso

Write this .ISO on a usb key with Etcher or other!

Start your computer on this usb key!

#1 Install raspbian for x86
When raspbian is installed open a terminal and write:

sudo raspi-config
 
in the raspi-config menu go to:
 
1 (System Options)

S5 (Boot option)

B2 (AutoLogin console)

Enable SSH:

Return to top of raspi-config menu

5 (Interfacing Options)

P2 SSH

Choose Yes in “Would you like the SSH server to be enabled?”

Go to Finish at the bottom right

restarted

#2 Write the command: 

ls /dev/serial/by-id/

This will give you the link to write in [mcu] of printer.cfg

Configure your Wi-Fi with: (You can use an ethernet cable if you have no wifi)

sudo raspi-config

1 and S1 (Wireless LAN)

#3 Install the kiauh scripts:

sudo apt-get install git -y

git clone https://github.com/th33xitus/kiauh.git

Open kiauh:

cd kiauh

./kiauh.sh

Install :

Klipper,moonraker,Fluidd and quit kiauh and install
the dependencies for Klipperscreen the #3 of the tutorial!

#4 To be able to install klipperscreen you need to install it's dependencies:

sudo apt-get update

sudo apt-get upgrade

sudo apt install libcairo2-dev pkg-config

sudo apt install python-gi-cairo

sudo apt install libgirepository1.0-dev

#5 Open kiauh and install Klipperscreen

#6 Add mouse cursor in Klipperscreen:

Go in :

klipper_config with this command:

CD..

cd klipper_config

Then this command:

sudo nano KlipperScreen.conf

and add this line:

show_cursor: True

ctrl+O and Enter to save

ctrl+X and Enter to quit nano

#7 Add the line (Write it so it's first):

needs_root_rights=yes
 
in this:

sudo nano /etc/X11/Xwrapper.config

ctrl+O and Enter to save

ctrl+X and Enter to quit nano

#8 At the end of having all installed for klipperscreen: (Not always mandatory)

sudo apt install xserver-xorg-legacy




here is klipper, fluidd, moonraker and Klipperscreen
is now installed and ready to use
with a mouse for a non-touch screen on your 3D printer!

Jérôme St-gelais (2022)
