# h2 Infra-as-code

### Koneen tiedot
- Device: X1 Carbon 5th Gen - Kabylake (Type 20HR, 20HQ) Laptop (ThinkPad) - Type 20HQ
- Serial Number: PF105Q96
- Processor:	Intel(R) Core(TM) i5-7300U CPU @ 2.60GHz   2.71 GHz
- Installed RAM:	8,00 GB (7,84 GB usable)
- Storage: 237GB
- System type:	64-bit operating system, x64-based processor
- Bios Version: N1MET37W 1.22

## x) Lue ja tiivistä

### Two Machine Virtual Network With Debian 11 Bullseye and Vagrant
#### (Tero karvinen, 2021)

### Salt Quickstart – Salt Stack Master and Slave on Ubuntu Linux
#### (Tero Karvinen, 2018)

### Hello Salt Infra-as-Code
#### (Tero Karvinen, 2014)

### Salt Vagrant - automatically provision one master and two slaves
#### (Tero Karvinen, 2023)

### Salt contributors: Salt overview
#### (Salt Project, n.d.)

## a) Hello Vagrant!
### 11.11.2024 Klo 14:00

Aloitin tehtävän tuttuun tapaan päivityksillä komennolla $ sudo apt-get update. Vagrant minulla oli jo ennestään asennettuna ja sen tarkistin komennolla $ vagrant --version.

![Screenshot 2024-11-13 222915](https://github.com/user-attachments/assets/d76b7d49-1e65-4224-9ae3-6ddaec53bfa7)

## b) Linux Vagrant
### Klo 14:05 

Seuraavaksi siirryin luomaan uutta Linux-virtuaalikonetta Vagrantilla. Aloitin luomalla Vagrant-tiedoston komennolla $ mkdir vagrant-siiri ja siirryin tiedostoon komennolla $ cd vagrant-siiri. 

![Screenshot 2024-11-13 203235](https://github.com/user-attachments/assets/e4b71547-5ade-4e34-b517-2af00109d4c5)

Heti perään päätin kuitenkin vaihtaa tiedoston nimeä, ja kävinkin muuttamassa sen muotoon bookworm-siiri. Siirryin tiedostoon uudestaan komennolla $ cd bookworm-siiri ja ajoin perään komennon $ vagrant up. Uuden virtuaalikoneen luominen sujui ongelmitta ja tarkistin sen tilanteen komennolla $ vagrant status. Virtuaalikone ilmestyi myös VirtualBogin manageriin.

![Screenshot 2024-11-13 222654](https://github.com/user-attachments/assets/f90dabc6-3459-4107-81d9-b7c0ffa10a5f)

![Screenshot 2024-11-13 222710](https://github.com/user-attachments/assets/7a47b01e-8560-4797-926e-13fd6e47785d)

![Screenshot 2024-11-14 125218](https://github.com/user-attachments/assets/9479e1ef-8f45-4f70-9553-0c320921f4ab)


## c) Kaksin kaunihimpi
### Klo

## d) Herra-orja verkossa
### Klo

## e) Hei infrakoodi!
### Klo

## f) Aja esimerkki sls-tiedostosi verkon yli orjalla
### Klo

## g) Tee sls-tiedosto, joka käyttää vähintään kahta eri tilafunktiota näistä: package, file, service, user.
### Klo

## h) Top file
### Klo

## Lähteet

Palvelinten hallinta. Tero Karvinen. Syksy 2024. Luettavissa: https://terokarvinen.com/palvelinten-hallinta/

Two Machine Virtual Network With Debian 11 Bullseye and Vagrant. Tero Karvinen. 2021. Luettavissa: https://terokarvinen.com/2021/two-machine-virtual-network-with-debian-11-bullseye-and-vagrant/

Salt Quickstart – Salt Stack Master and Slave on Ubuntu Linux. Tero Karvinen. 2018. Luettavissa: https://terokarvinen.com/2018/salt-quickstart-salt-stack-master-and-slave-on-ubuntu-linux/?fromSearch=salt%20quickstart%20salt%20stack%20master%20and%20slave%20on%20ubuntu%20linux

Hello Salt Infra-as-Code. Tero Karvinen. 2014. Luettavissa: https://terokarvinen.com/2024/hello-salt-infra-as-code/

Salt Vagrant - automatically provision one master and two slaves. Tero Karvinen. 2023. Luettavissa: https://terokarvinen.com/2023/salt-vagrant/#infra-as-code---your-wishes-as-a-text-file

Salt contributors: Salt overview. Salt Project. n.d. Luettavissa: https://docs.saltproject.io/salt/user-guide/en/latest/topics/overview.html#rules-of-yaml
