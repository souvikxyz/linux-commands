
mkdir music
touch song{1..10}.mp3
mv song*.mp3 music
ln -s music audio

sudo groupadd sysadmin
sudo groupadd manager
sudo useradd bob
sudo useradd rob
sudo useradd max
sudo passwd bob
type linux123 in password prompt
sudo passwd rob
type linux123 in password prompt
sudo passwd max
type linux123 in password prompt
sudo usermod -g sysadmin bob
sudo usermod -g sysadmin rob
sudo usermod -g sysadmin max
sudo usermod -G manager bob
sudo usermod -G manager rob

nano /etc/passwd
Edit 'max❌1003:1005::/home/max:/bin/bash' to 'max❌1003:1005::/home/max:/bin/false'
Press 'ctrl-x' and 'Enter' to save it.
sudo chage -d 0 bob
sudo chage -E `date -d "30 days" +"%Y-%m-%d"` max

mkdir /home/manager
sudo chgrp manager /home/manager
sudo chmod 2770 /home/manager

sudo useradd -u 4223 gabriel

mkdir /tmp/var
'tar -cvjf /tmp/var/archive.tar.bz2 /etc/hosts'

cat /etc/services | grep udp > udp_services.txt

'top' then 'shift+f' then 's' to set the sort then 'esc' to go back 

'echo 'alias stats="/bin/uptime"' >> ~/.bashrc'
and 'source ~/.bashrc'

'vim test.txt' and press 'i' to enter insert mode and edit the file
press 'esc' for command mode and -->
':wq' for save and exit and ':q' for exit only

sudo apt install firewalld
sudo systemctl enable firewalld
sudo systemctl restart firewalld
sudo firewall-cmd --get-default-zone
sudo firewall-cmd --set-default-zone=dmz
sudo firewall-cmd --get-zones > zones.txt

sudo firewall-cmd --permanent --zone=public --add-port=8080/tcp'
sudo firewall-cmd --list-ports >> zones.txt

sudo firewall-cmd --zone=public --permanent --add-forward-port=port=80:proto=tcp:toport=8080'
hostname -I
