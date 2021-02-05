#! /bin/bash

printf "Installing RDP Be Patience... username: rcode password: 123456 " >&2

{

sudo useradd -m rcode

sudo adduser rcode sudo

echo 'rcode:123456' | sudo chpasswd

sed -i 's/\/bin\/sh/\/bin\/bash/g' /etc/passwd

sudo apt-get update

wget https://dl.google.com/linux/direct/chrome-remote-desktop_current_amd64.deb

sudo dpkg --install chrome-remote-desktop_current_amd64.deb

sudo apt install --assume-yes --fix-broken

sudo DEBIAN_FRONTEND=noninteractive \

apt install --assume-yes xfce4 desktop-base

sudo bash -c 'echo "exec /etc/X11/Xsession /usr/bin/xfce4-session" > /etc/chrome-remote-desktop-session'  

sudo apt install --assume-yes xscreensaver

sudo systemctl disable lightdm.service

wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb

sudo dpkg --install google-chrome-stable_current_amd64.deb

sudo apt install --assume-yes --fix-broken

sudo apt install nautilus nano -y 

sudo adduser rcode chrome-remote-desktop

} &> /dev/null &&

printf "\nSetup Complete " >&2 ||

printf "\nError Occured " >&2

printf '\nCheck https://remotedesktop.google.com/headless  Copy Command Of Debian Linux And Paste Down\n'

#read -p "Paste Here: " CRP

#su - rcode -c """$CRP"""

su - rcode -c """DISPLAY= /opt/google/chrome-remote-desktop/start-host --code="4/0AY0e-g6ZQdE824dDtZrAZEyf4t-fchWNL7eINvScI3GnRG8DldHWFM-COQg6MXc_EijxEw" --redirect-url="https://remotedesktop.google.com/_/oauthredirect" --name=$(hostname)"""

printf 'Check https://remotedesktop.google.com/access/ \n\n'

if sudo apt-get upgrade &> /dev/null

then

    printf "\n\nUpgrade Completed " >&2

else

    printf "\n\nError Occured " >&2

fi
