# Debian install process

Used Rufus on Windows to setup bootable USB for the Debian ISO

My optiplex has UEFI, so I used GPT for the partition scheme
If using legacy boot, MBR would be required
On my machine, I had to enter the BIOS/UEFI setup and change the Boot List Option to UEFI

I mostly followed default debian installation using the gui interface

# Setting up Sudo
SSH into the server
Run su root to elevate to root privilege
run apt install sudo nano (nano because I wanted a text editor)
run /usr/sbin/usermod -aG sudo <username>
