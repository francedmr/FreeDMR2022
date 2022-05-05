### FreeDMR Peer Server is a (now very diverged) fork of the hblink3 project ###

FreeDMR Peer Server - software to assist in building a peer mesh network

sudo apt update 
sudo apt upgrade 
sudo apt install git 
sudo apt install python3-pip 
sudo apt install python-pip                 (inutile en Debian 11) 
python3 -m pip install pip --upgrade        (inutile en Debian 11) 
cd /opt 
git clone https://gitlab.hacknix.net/hacknix/FreeDMR.git
cd /opt/FreeDMR
chmod +x install.sh
sudo ./install.sh
cp FreeDMR-SAMPLE.cfg hblink.cfg            (ici, on copie le fichier d’exemple en fichier de configuration)
cp rules_SAMPLE.py rules.py                 (idem ici pour le fichier de configuration des TG)

nano /opt/FreeDMR/hblink.cfg 


nano /opt/FreeDMR/rules.py

cp utils/freedmr.service /lib/systemd/system/
cp utils/hotspot_proxy.service /lib/systemd/system

#Vèrifications des fichiers commandes:

nano /lib/systemd/system/freedmr.service
nano /lib/systemd/system/hotspot_proxy.service

#Mise en route du serveur & vèrification
 
systemctl enable freedmr 
systemctl start freedmr 
systemctl status freedmr

systemctl enable hotspot_proxy 
systemctl start hotspot_proxy 
systemctl status hotspot_proxy
