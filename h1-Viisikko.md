# h1 - Viisikko

### Koneen tiedot
- Device: X1 Carbon 5th Gen - Kabylake (Type 20HR, 20HQ) Laptop (ThinkPad) - Type 20HQ
- Serial Number: PF105Q96
- Processor:	Intel(R) Core(TM) i5-7300U CPU @ 2.60GHz   2.71 GHz
- Installed RAM:	8,00 GB (7,84 GB usable)
- Storage: 237GB
- System type:	64-bit operating system, x64-based processor
- Bios Version: N1MET37W 1.22

## x) Lue ja tiivistä

### Run Salt Command Locally
#### (https://terokarvinen.com/2021/salt-run-command-locally/)
- Salt-komentojen suorittamisesta paikallisesti on hyötyä harjoittelussa, testaamisessa ja nopeissa asennuksissa
- Samat toiminnot toimivat sekä Linuxissa että Windowsissa
- Tärkeimmät tilatoiminnot ovat pkg (paketti), file (tiedosto), service (palvelu), user (käyttäjä) ja cmd (komento)
- Cmd.run -komento täytyy tehdä idempotentiksi, jotta se suoritetaan vain tarvittaessa
- Suositeltavaa on käyttää file, service tai user -toimintoja cmd.run -toiminnon sijaan

### Salt Quickstart – Salt Stack Master and Slave on Ubuntu Linux
#### (https://terokarvinen.com/2018/03/28/salt-quickstart-salt-stack-master-and-slave-on-ubuntu-linux/)
- Saltin avulla voidaan hallita tuhansia tietokoneita
- Vain pääpalvelimella on oltava julkinen palvelin ja tunnettu osoite
- Ohjattavat tietokoneet, eli orjat, voivat olla missä tahansa (tuntemattomassa osoitteessa, palomuurin takana yms.) ja silti niitä on mahollista hallita

### Raportin kirjoittaminen
##### (https://terokarvinen.com/2006/06/04/raportin-kirjoittaminen-4/)
- Raportin tulee olla selkeä sekä helposti ymmärrettävissä ja toistettavissa
- On hyvä kertoa mikä onnistui, mikä ei onnistunut sekä miten ja missä ajassa testaaminen suoritettiin
- Raportissa tulee viitata lähteisiin 
- Raportin tulee olla todenmukainen ja aidosti omien tekojen ja ajatusten tuotos

## a) Debian 12-Bookworm asennus virtuaalikoneeseen

Debian 12-bookwormin asennus valmiina virtuaalikoneella.

## b) Asenna Salt virtuaalikoneeseen

Aloitin tehtävän päivityksillä, sillä edellisestä pävityskerrasta oli vierähtänyt jo tovi.

![Screenshot 2024-10-29 200015](https://github.com/user-attachments/assets/2606006c-d93d-4517-b2eb-393e470e04bd)

Seuraavaksi siirryin Salt:in asennukseen. Komento $ sudo mkdir /etc/apt/keyrings herjasi, että hakemisto löytyy jo, mutta sen puolesta kaikki ok. Jatkoin alla olevan kuvan ohjeiden mukaisesti, jotka löytyvät Teron kurssimateriaalista (https://terokarvinen.com/palvelinten-hallinta/). Ensimmäisen komennon kanssa oli pieniä haasteita oikeinkirjoituksen kanssa, mutta ei sen kummempaa ongelmaa asennuksessa.

![Screenshot 2024-10-29 210052](https://github.com/user-attachments/assets/09ff3ad2-40bf-4f51-af1a-ac19cbacdeb6)

![Screenshot 2024-10-29 203614](https://github.com/user-attachments/assets/8d448107-0706-4240-8a8c-c756d97efa8d)

Minionin asennus:

![Screenshot 2024-10-29 203855](https://github.com/user-attachments/assets/fe011955-6b50-4b77-a9b8-05e8d15b333b)

Päivittelin vielä uudemman kerran asennuksen jälkeen, jotta kaikki on varmasti ajan tasalla:

![Screenshot 2024-10-29 210039](https://github.com/user-attachments/assets/46560886-ec97-4f78-b82d-1e79bfd55ccd)

Ja tarkistin vielä komennolla $ sudo salt-call --version, että asennus on mennyt läpi. Hyvältä näytti.

![Screenshot 2024-10-29 205836](https://github.com/user-attachments/assets/1be6a8ec-802c-4354-b47b-d729e2da9f0e)

## c) Viisi tärkeintä

Seuraavaksi siirryin Saltin viiden tärkeimmän tilafunktion pariin, eli pkg, file, service, user, cmd.

### pkg
- Pkg-moduulilla voidaan asentaa, päivittää, poistaa ja tyhjentää sovelluksia (VMware, Inc. 2023).

Esimerkkinä halusin selvittää komennolla $ sudo salt-call --locall -l info state.single pkg.installed apache2, onko apache2 asennettuna. Tuloksena oli terminaain tulostunut listaus apache2-sovellukseen liittyvistä tiedoista. 

Listauksen mukaan apache2 on asennettuna.

![Screenshot 2024-10-29 212602](https://github.com/user-attachments/assets/0de17baa-5cde-4d7f-b962-98b700e0fe3a)

### file
- File-moduulilla voidaan hallita tiedostojen ja hakemistojen tietoja, kuten niiden olemassaolon ja sisällön (VMware, inc. 2023).

Esimerkkinä halusin selvittää komennolla $ sudo salt-call --local -l info state.single file.managed /home/siival/kissa.txt, löytyykö /home/siival/ hakemistopolusta "kissa.txt" -tiedosto. Tuloksena terminaaliin tulostui listaus, josta ilmenee, että "kissa.txt"-tiedosto on olemassa eikä siihen ole tehty muutoksia.
  
![Screenshot 2024-10-29 212915](https://github.com/user-attachments/assets/c79ced6b-b956-4747-a02f-0c9fa04ec90c)

### service
- Service-moduulilla hallinnoidaan demoneiden käynnistystä ja lopetusta. Demonit voidaan määritellä joko käynnissä oleviksi tai kuolleiksi (VMware, Inc. 2023).

Esimerkkinä halusin selvittää komennolla $ sudo salt-call --local -l info state.single service.running apache2, onko apache2 käynnissä. Tuloksena termiaaliin tulostui listaus, jonka mukaan apache2 on käynnissä.

![Screenshot 2024-10-29 213131](https://github.com/user-attachments/assets/7c9176d6-902c-44ca-b732-6d47ba60926f)

### user
- User-moduulilla hallitaan ja luodaan käyttäjäasetuksia. Lisäksi käyttäjät voidaan asettaa joko poissaoleviksi "absent" tai läsnä oleviksi "present" (VMware, Inc. 2023).

Esimerkkinä halusin selvittää komennolla $ sudo salt-call --local -l info state.single user.present siival, onko käyttäjä siival (minä itse) läsnä. Tuloksena terminaaliin tulostui listaus, josta ilmenee, että käyttäjä "siival" on "present" ja kaikki on käyttäjän osalta ajantasalla.

![Screenshot 2024-10-29 213235](https://github.com/user-attachments/assets/25dab66b-a6c2-4c60-96ee-285805688907)

### cmd
- Cmd-moduulilla halltaan suoritettujen komentojen täytäntöönpanoa. Cmd-moduuli mahdollistaa komentojen suorittamisen tiettyjen olosuhteiden puitteista (VMware, Inc. 2023).

Ésimerkkinä halusin komennolla $ sudo salt-call --locall -l state.single cmd.run ´touch /home/siival/koira.txt´ creates="/home/siival/koira.txt", luoda "koira.txt"-tiedoston, mikäli sellaista ei ole jo olemassa. "creates="/home/siival/koira.txt"-ehto varmistaa, että komento suoritetaan vain, jos "koira.txt"-tiedostoa ei vielä ole olemassa. Muuten komento jää suorittamatta.

Tuloksena komento suoritettiin, sillä "koira.txt"-tiedostoa ei ollut ja kyseinen tiedosto luotiin.

![Screenshot 2024-10-29 213536](https://github.com/user-attachments/assets/5a4f8b22-5cd8-4dec-b622-aaedbe833f34)

![Screenshot 2024-10-29 213559](https://github.com/user-attachments/assets/1f1091ee-40f2-47cf-aced-7a9a46c6f4d6)

## d) Idempotentti

idempotentti ilmeni jo edellisen tehtävän viimeisessä osiossa "cmd", jossa "koira.txt"-tiedostoa ei ollut alkujaan olemassa, joten "create="/home/siival/koira.txt"-ehtoa ei toteutettu, sillä ehto ei täyttynyt. Näin ollen "koira.txt"-tiedosto luotiin.

## e) Herra-orja

## Lähteet

Salt table of Contents. VMware, Inc. 2023. Luettavissa: https://docs.saltproject.io/en/latest/contents.html

Palvelinten hallinta. Tero Karvinen. Syksy 2024. Luettavissa: https://terokarvinen.com/palvelinten-hallinta/

