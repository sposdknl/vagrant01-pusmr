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

##Dokumentace Miroslav Puš, 10.10.2025

-ve repository jsem si vytvořil složku Server, do které jsem se před příkazový řádek dostal a pomocí "vagrant init" vytvořil Vagrantfile
-do Vagrantfile jsem vložil základní konfiguraci Debian a upravil port na 80-8080 a do příkazového řádku napsal "vagrant up"
-pomocí "vagrant ssh-config" jsem našel lokaci klíče, který jsem pomocí PuttyGen upravil na veřejný a přidal ho do složky k Vagrantfile
-do Vagrantfile jsem přidal:  "config.vm.provision "file", source: "ssh.pub", destination: "~/.ssh/me.pub" " a "cat /home/vagrant/.ssh/me.pub >> /home/vagrant/.ssh/authorized_keys"
-vytvořil jsem i soukromý klíč kvůli automatickému přihlášení do putty
-poté jsem použil:
        sudo apt update -y
        sudo apt install -y apache2
        sudo systemctl enable apache2
        sudo systemctl start apache2
        if command -v ufw >/dev/null 2>&1; then
            sudo ufw allow 'Apache'
        fi
tímto jsem stáhnul a povolil Apache2
-jestli Apache funguje jsem ověřil tím, že jsem napsal "localhost:8080" do prohlížeče