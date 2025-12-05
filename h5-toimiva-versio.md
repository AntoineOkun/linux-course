# Toimiva versio

## Ympäristö

### Fyysinen kone

- MacBook Air M3

### Virtuaali kone

- UTM
- Debian 12 (bookworm)
  - Muisti 4 GB
  - Tila 80 GB

## Tiivistelmä

- Chacon and Straub 2014
  - Gitin esittelyä; ero muihin vastaanvanlaisiin alustoihin
    
- git add . && git commit; git pull && git push
  - Ensimmäinen komento siirtää haluamat tiedostot eräänlaiselle puskurivyöhykkeelle, toinen lisäys lukitsee siirrettävän version tiedostosta ja antaa mahdollisuuden lisätä kommentin siirron kylkeen, kolmas komento tarkistaa kansioin yhtäläisyydet ja tarvittaessa päivittää työtilaan muualta tulleet muutokset, neljäs komento vie haluamat tiedot gittiin. ([git](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)
    
- Suolaxin historia (käännetyssä järjestyksessä)
  - Käyttäjäohjeiden kohennus
  - README.md tiedoston muokkaus
  - Lempiohjelmien lisäyksiä ja asennettujen ohjelmien listaus top-fileen
  - Lempiohjelmien asennuksien ajon lisäys
  - Makefilen lisäys
  - Hello world -modulin lisäys
  - README.md tiedoston kohennusta
  - Alkuperäinen commit, eli repon luonti


## a)

Loin nettisivujen kautta uuden snow -repon ja lisäsin siihen automaatiolla lisenssi ja readme -sivustot. Kuvaukseksi laitoin "snow".

<img width="914" height="492" alt="Screenshot 2025-12-05 at 11 06 48" src="https://github.com/user-attachments/assets/86e64bca-f7d9-4d87-9843-c77359b377d7" />

## b)

Kloonasin tekemäni repon koneelleni komennolla 'git clone git@github.com:AntoineOkun/snow.git'. Tein muutoksen README.md tiedostoon microlla ja päivitin 'push' -komennolla tiedoston gittiin.

<img width="911" height="491" alt="Screenshot 2025-12-05 at 11 11 25" src="https://github.com/user-attachments/assets/1609602b-47c8-4225-8b63-451f9f4b24fe" />

## c)

Tein muutoksen README.md tiedostoon, jonka en halunnutkaan päivittyvän ja käytin komentoa 'git reset --hard'.

<img width="382" height="42" alt="Screenshot 2025-12-05 at 11 15 02" src="https://github.com/user-attachments/assets/8af12159-04ec-44cd-a600-2fe848397e84" />

## d)

Käytin komentoa 'git log --patch --color|less -R' nähdäkseni kaiken tekemäni snow -repossa.

<img width="454" height="927" alt="Screenshot 2025-12-05 at 11 18 29" src="https://github.com/user-attachments/assets/ee7baef2-7e6d-457a-a8e0-34567fb9bbdc" />

Historiassa näkyy repon luonti "Initial commit" vaiheena, jonka jälkeen päivitykseni README.md tiedostoon. Sitä seuraa vielä yksi päivitys samaiseen, kun yritin 'reset --hard' komentoa väärässä kohdassa.

## e)

Ajoin tilat Tero Karviselta kloonatusta kansiosta komennolla 'sudo salt-call --local --file-root /home/debian/suolax/suolax/srv/salt/ state.apply' käyttäen Teron top-filea, tällaisin lopputuloksin:

<img width="720" height="1052" alt="Screenshot 2025-12-05 at 11 28 37" src="https://github.com/user-attachments/assets/234d9493-6a65-4e96-b37c-2ae8b18ddbd6" />


## Lähteet

Karvinen, 2025: https://terokarvinen.com/palvelinten-hallinta/
Git, Getting started: https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F
Git, Git Basics: https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository

