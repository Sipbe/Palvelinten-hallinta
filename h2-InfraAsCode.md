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

### Valmista 14.20

## c) Kaksin kaunihimpi
### Klo 14.20

Homma alkoi uuden Vagrant-tiedoston luomisella komennolla $ mkdir kaksikaunista. Sen jälkeen siirryin tiedostoon komennolla $ cd kaksikaunista ja komennolla $ nano Vagrantfile siirryin muokkaamaan Vagrantfilea ja lisäsin sinne Teron ohjeiden (Tero Karvinen, 2021) mukaisen tiedoston.

![Screenshot 2024-11-14 141813](https://github.com/user-attachments/assets/feddaa6c-779c-428b-b53c-473e719ec004)

![Screenshot 2024-11-14 141942](https://github.com/user-attachments/assets/a6a6d307-5d37-4d43-bf8f-91c0c184fae0)

![Screenshot 2024-11-20 150027](https://github.com/user-attachments/assets/fc3eb05e-7fab-43a6-a406-5e15c177bdc1)

Tässä kohtaa komento $ vagrant status pitäisi näyttää kaksi uutta virtuaalikonetta. Tarkistin suorittamalla komennon ja siellä olivat.

![Screenshot 2024-11-14 142124](https://github.com/user-attachments/assets/09d107fe-163c-4a19-8bb3-c2c97e54a982)

Ei muuta kuin komento $ vagrant up suoritukseen ja koneiden luontiin. Kaiki sujui ok ja komennolla $ vagrant status tarkistin vielä koneiden tilanteen ja kurkkasin myös VirtualBoxin puolelta, että koneet olivat ilmestyneet myös sinne. All good.

![Screenshot 2024-11-20 151925](https://github.com/user-attachments/assets/c747fc22-fb65-49d5-836d-616bf322adcb)

![Screenshot 2024-11-20 142117](https://github.com/user-attachments/assets/00cb64e0-772b-4fd2-8fdf-0400b4d6e573)

![Screenshot 2024-11-20 150526](https://github.com/user-attachments/assets/002676f5-f38b-4f91-9889-5de06b808890)

Seuraavaksi otin vuorollaan yhteyden molempiin koneisiin komennolla $ vagrant ssh  t001 ja t002. Pingasin koneet toisiinsa ja poistuin koneilta komennolla $ exit.

![Screenshot 2024-11-20 142452](https://github.com/user-attachments/assets/9bac5ac3-31b3-4ee5-b0c0-31c3b91490e4)

![Screenshot 2024-11-20 142614](https://github.com/user-attachments/assets/affaee05-b6ce-48cd-ac9e-a24bda1c323c)

### Valmista 14.50

## d) Herra-orja verkossa
### Klo 14.50


### Valmista 16.00

## e) Hei infrakoodi!
### Klo 16.00

### Valmista 16.10

## f) Aja esimerkki sls-tiedostosi verkon yli orjalla
### Klo 16.10

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
