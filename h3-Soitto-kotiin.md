# Soitto kotiin

## Ympäristö

### Fyysinen kone

- MacBook Air M3

### Virtuaali kone

- UTM
- Debian 12 (bookworm)
  - Muisti 4 GB
  - Tila 80 GB

## Tiivistelmä

### Karvinen 2021, Two Machine Virtual Network With Debian 11 Bullseye and Vagrant
- Ytimekäs kirjoitus, kuinka saadaan Vagrant asennettua ja virtuaalikoneet pystyyn.

### Karvinen 2018, Salt Quickstart – Salt Stack Master and Slave on Ubuntu Linux
- Saltin herra-orja toimintain asennuksen ja toiminnan esittely.

### Karvinen 2023, Salt Vagrant - automatically provision one master and two slaves
- Esimerkki siitä, kuinka tehdään kaikkia orjia koskeva tervehdys, ja kuinka ne tuhotaan.



**-------------------- Erheeni alku ----------------------**

## a)

- Ensin asennan Vagrantin *https://developer.hashicorp.com/vagrant/install* -sivustolta ja sieltä löytyvällä Ubuntu/Debian kohdan komennolla.
    - Asennus näyttää onnistuneen:
      
      <img width="307" height="44" alt="Screenshot 2025-11-08 at 11 06 53" src="https://github.com/user-attachments/assets/6d9a86fc-3fcc-41db-9f44-38ce6b10585e" />

## b)

- Teen ensin projektilleni uuden kansion ohjeen (Karvinen, 2021) mukaan:
  
<img width="401" height="44" alt="Screenshot 2025-11-08 at 11 11 19" src="https://github.com/user-attachments/assets/99190cf0-d967-4372-a3fa-9df74483e3f3" />

ja kopioin tekemääni Vagrantfile -tekstitiedostoon samaisesta ohjeesta scriptin, joka pystyttää minulle kaksi virtuaalikonetta.

- Niitä ajaessani huomaan, että skippasin alussa VirtualBoxin asennuksen. Tämä aiheuttaa todella paljon päänvaivaa:
  - Tein ensin ohjeiden mukaan ja mitään ei tapahtunut
  - Sitten yritin muutella ensimmäisen kohdan lataus -osion osoitetta, mutta niinkään en onnistunut.
  - En ole vielä tottunut tarpeeksi tähän raportointi- ja lokityyliin, joten kohdatessani tällaisia ongelmia, jätän kirjoittamisen ja alan brutforsaamaan ratkaisua.
  - Seurailin kuitenkin jälkiäni mahdollisimman tarkasti takaisin ja yritin kumota kaiken.
 
- Koska en onnistunut tässä millään, kysyin ChatGPT:ltä kuinka voisin saada puuttuvan libvirtin Debianille. Tässä sen neuvot:
  - Ensin *sudo apt install -y qemu-kvm libvirt-daemon-system libvirt-clients ebtables dnsmasq*
  - Sitten *vagrant plugin install vagrant-libvirt*
  - Ja sitten bootti

- Tällä kertaa pääsin *vagrant up* -komennolla hiukan pidemmälle, mutta lopulta error sai.

- Virheitä virheiden perään. Pitää yrittää myöhemmin.

**-------------------- Erheeni loppu ----------------------**

Aloitin ***kaiken*** alusta. Asensin VirtualBoxille Macille sopivan Debian 13 järjestelmän. Taistelin sen kanssa hetken. Live -käyttistä ei ole Trixiellä armille. En saanut vaihdettua US näppäimistöä, en saanut "enabloitua" edes sudoa.

Siirryin siispä takaisin samalle polulle, jonka olen jo aikaisemmin kulkenut, ja latasin itselleni uudelleen UTM:lle ja Macille sopivan Debian 12 -järjestelmän kuvan. Teen siitä heti aluksi kopion, jotta voin aloittaa helpommin tyhjästä tarvittaessa uudelleen.

Aloitan urakan asentamalla Linux-komentojen kertaussivuston(Karvinen 2020) lopusta litanjan ohjelmia.
  - En todellakaan tiedä, mikä on nyt eri tavoin, mutta heti kärkeen esimerkiksi *tree*n asennuksen jälkeen tree toimii, eikä näytä jotain jänniä ääkkösiä viivain tilalla.
Sitten apassi, saltin ja vagrantin asennus... ja takaisin tehtävänantoihin:


## a)

- ***No niiiiin*** yritän asentaa Vagrantin ohjeiden mukaan ja katsotaan kuinka käy. Se onnistu hienosti:

  <img width="318" height="62" alt="Screenshot 2025-11-09 at 16 21 05" src="https://github.com/user-attachments/assets/65be73a3-2160-4d6f-b769-cb2bbc304540" />

- Virtualboxin kanssa on tälläkin kierroksella ongelmia! Olen neuvoton jatkamaan, mutta teen kuitenkin vielä *Vagrantfile*n ja ajamisen jälkeen näyttää tutulta:

  <img width="1090" height="400" alt="Screenshot 2025-11-09 at 16 31 22" src="https://github.com/user-attachments/assets/b38a6156-cc2d-416a-88a4-c20bf3d807e2" />

Lähden taa vähän matkaa seuraamaan tätä loputonta showta ja katsotaan, mitä saa:

  <img width="883" height="41" alt="Screenshot 2025-11-09 at 16 36 54" src="https://github.com/user-attachments/assets/15d74737-4fe3-41f5-b43e-5e285202d87b" />
  
  Ensimmäinen ohje. Katsotaan, mitä siitä seuraa:

  <img width="684" height="190" alt="Screenshot 2025-11-09 at 16 38 57" src="https://github.com/user-attachments/assets/0e16c6ac-07a7-476f-a411-c4b51c29097f" />

  Sentään jotain uutta. Auttoiko se *Vagrantfilen* ajamisessa:

  <img width="1099" height="404" alt="Screenshot 2025-11-09 at 16 40 14" src="https://github.com/user-attachments/assets/fc80692e-e8d9-4e03-bf1e-bb71e34e414e" />

  Ei auttanut.

  Tämä riittää minulle tällä kertaa.


## b)

**---**


## c)

**---**

## d)

**---**

## Lähteet:

Vagrantin asennus, [https://developer.hashicorp.com/vagrant/install]

ChatGPT, [https://openai.com]

Karvinen, 2020: [https://terokarvinen.com/2020/command-line-basics-revisited/]




