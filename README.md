[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/vMONzaIj)
# VG1-APACHE

The appearance of independent work - Vagrant, SSH and Apache

Samostana prace - Vagrant, SSH, a Apache

- V Teams kliknete na odkaz Github Classrom, tim se Vam vytvori Vas repository pro toto zadani
- Vytvorte si Clon Vaseho prvniho repository
- Vytvorte v nem adresar pro Vas prvni server vytvoreny pomoci Vagrant
- Do nej vlozte Vagrantfile z projektoveho repository - Vyberte si oblibenou Linux distribuci [2025-sposdk-osy](https://github.com/sposdknl/2025-sposdk-osy/)
- Upravte Vagrantfile, aby fungoval portforward z portu 80 na port 8080
- Zajistete import Vaseho SSH verejneho klice do instalovane VM
- Zajistete instalaci web serveru Apache pomoci scriptu psaneho v bash
- Vse bude konfigurovano automaticky, po vytvoreni VM bude funkcni SSH z Putty autentizovano pomoci SSH klice a na http://localhost:8080 bude bezet Webserver Apache 
- Upravre README tak, aby bylo jasne co Vas projekt dela, strucne zdokumentujte.
- Funkcni Vagrant deployment bude pridan do Vaseho repository na Guthub

## Documentation

- [Vagrant - Shell Provisioner](https://developer.hashicorp.com/vagrant/docs/provisioning/shell)
- [Vagrant - File Provisioner](https://developer.hashicorp.com/vagrant/docs/provisioning/file)

## Examples commands

```console
git clone https://github.com/sposdknl/VASPROJEKT
cd VASPROJEKT && mkdir LinuxServer && cd LinuxServer
cp ../2025-sposdk-osy/XYZ/Vagrantfile Vagrantfile
vim Vagrantfile
vim install-apache.sh
vim .gitignore

git add LinuxServer/*
git commit "Add new VM + Automatizace"
git push
```
