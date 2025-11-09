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



# -------------- Erheeni ----------------

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

# -------------- Erheeni ----------------

Aloitin ***kaiken*** alusta. Asensin VirtualBoxille Macille sopivan Debian 13 järjestelmän. Taistelin sen kanssa hetken. Live -käyttistä ei ole Trixiellä armille. En saanut vaihdettua US näppäimistöä, en saanut "enabloitua" edes sudoa.

Siirryin siispä takaisin samalle polulle, jonka olen jo aikaisemmin kulkenut, ja latasin itselleni uudelleen UTM:lle ja Macille sopivan Debian 12 -järjestelmän kuvan. Teen siitä heti aluksi kopion, jotta voin aloittaa helpommin tyhjästä tarvittaessa uudelleen.



- 
## c)

## d)

## Lähteet:

Vagrantin asennus, [https://developer.hashicorp.com/vagrant/install]

ChatGPT, [https://openai.com]


