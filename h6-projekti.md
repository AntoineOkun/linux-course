# Pariprojekti - Samba and UFW with Salt

## Ympäristö


### Fyysinen kone

- MacBook Air M3

### Virtuaali kone

- UTM
- Debian 12 (bookworm)
  - Muisti 4 GB
  - Tila 80 GB

## Suunnittelu

- Mikon ideasta lähdimme toteuttamaan Samba tiedostopalvelimen käyttöä. Hän sai osakseen Samban ja minä osani Saltista ja UFW:n asetukset.

## Rakentaminen

- Ensin tein asennus kansion, jossa init.sls -tiedosto hoitaa tarvittavan Samban ja UFW:n asennukset:

<img width="167" height="105" alt="Screenshot 2025-11-30 at 18 45 08" src="https://github.com/user-attachments/assets/f00370c9-503c-4417-a880-a67bb372f18a" />

- Välissä tein top.sls tiedoston, kun luulin olevani helpoilla palomuurin asetusten kanssa.

  <img width="155" height="108" alt="Screenshot 2025-11-30 at 18 48 21" src="https://github.com/user-attachments/assets/29c31c12-6578-4a4e-9488-01ca53b4021e" />

- Palomuurin asetusten kanssa oli suurin vääntö, koska en tiennyt kuinka idempotenssi saataisiin toteutettua. Olin laittanut jokaisen portinmuunnoksen samaan cmd.run -komentolinjaan, jolloin ne ajettiin jokainen... joka kerta.

<img width="526" height="370" alt="Screenshot 2025-11-29 at 15 46 12" src="https://github.com/user-attachments/assets/54c1df46-33ab-48cf-9ee6-b6df8d6e4023" />

<img width="231" height="103" alt="Screenshot 2025-11-29 at 15 46 24" src="https://github.com/user-attachments/assets/b1a043c0-4af3-447a-9d0d-d58f3b461f3f" />

Lopulta laitoin kaikki komennot seuraavan kaltaiseen muotoon:

<img width="415" height="84" alt="Screenshot 2025-11-30 at 18 34 20" src="https://github.com/user-attachments/assets/9b1003d2-7431-4958-ab2c-b448d476e7aa" />

Ja kaikki toimi.

- Rakentaminen oli minulle todella vaikeaa. Yritin monituisesti saada toista konetta luotua kloonaten ja yksilöiden asetuksia, mutta turhaan; en saanut klooni koneita alkuasetuksia pidemmälle,
  koska alkuperäisessä "koneessa" oli jotain korruptoitunut tai kloonaus korruptoi kloonit. Latasin sitten moneen vaiheen jälkeen uuden "kuvan" ja sain sen onneksi ylös ja testikuntoon. Ja parahiksi näin,
  sillä init.sls -tiedostot olivat toiminnassa.
  
  <img width="254" height="148" alt="Screenshot 2025-11-30 at 18 30 04" src="https://github.com/user-attachments/assets/0b146323-a5a5-43db-be4f-56fcf7ef4889" />

## Lähteet

- UFW [help.ubuntu.com](https://help.ubuntu.com/community/UFW)
- UFW & Samba [askubuntu.com](https://askubuntu.com/questions/36608/ufw-firewall-still-blocking-smb-despite-adding-rules)
- Salt project [SALT.STATES.CMD](https://docs.saltproject.io/en/latest/ref/states/all/salt.states.cmd.html#salt.states.cmd.run)
