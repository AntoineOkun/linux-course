# Pkg-file-service

## Ympäristö

### Fyysinen kone

- MacBook Air M3

### Virtuaali kone

- UTM
- Debian 12 (bookworm)
  - Muisti 4 GB
  - Tila 80 GB

## Tiivistelmä

### Pkg-File-Service – Control Daemons with Salt – Change SSH Server Port:

-  Kertomus siitä, kuinka saadaan ssh ensin asennettua ja sitten ajetttua sitä ylläpitävä init -tiedosto. Sitten mallinnusta yhteyden testauksesta omille hallittaville koneille.

## a)

Tein ohjetta (Karvinen, 2018) vastaavan sshd_config tiedoston kohtaan /srv/salt/, ja lisäsin siihen kaksi porttia:

<img width="562" height="899" alt="Screenshot 2025-11-16 at 16 14 13" src="https://github.com/user-attachments/assets/374301b3-9a1b-4e41-94c0-625023a5a105" />



## Lähteet

- Karvinen, 2018: [https://terokarvinen.com/2018/04/03/pkg-file-service-control-daemons-with-salt-change-ssh-server-port/?fromSearch=karvinen%20salt%20ssh]
