# Infraa koodina

## Ympäristö

### Fyysinen kone

- MacBook Air M3

### Virtuaali kone

- UTM
- Debian 12 (bookworm)
  - Muisti 4 GB
  - Tila 80 GB

## Tiivistelmä

### Karvinen 2014: Hello Salt Infra-as-Code
- Artikkelissa käydään läpi, kuinka saadaan tehtyä idempotentti scripti.

### Salt contributors: Salt overview
- YAMLin pikaperusteet.

### Salt contributors: The top file
- Top file -käsitteen nopea esittely.
  
## a) Hei infrakoodi!

Kaikki meni todella suoraviivaisesti ja helposti ohjeiden mukaan. Ensin tein *hello* -kansion, jonka jälkeen kirjoitin *init.sls* -tiedostoon:

<img width="308" height="99" alt="Screenshot 2025-10-31 at 10 26 20" src="https://github.com/user-attachments/assets/e734f4ef-4e49-44cc-8e4d-5c196969b93d" />

Komennon *sudo salt-call --local state.apply hello* jälkeen tuli odotettu tuloste:

<img width="394" height="325" alt="Screenshot 2025-10-31 at 10 27 31" src="https://github.com/user-attachments/assets/f3018220-757c-4ffb-9492-e1990b431753" />

Vielä testaus, onko tiedosto halutussa paikassaan:

<img width="314" height="42" alt="Screenshot 2025-10-31 at 10 28 55" src="https://github.com/user-attachments/assets/6104539a-0ed4-4629-b6ec-6c3725a416b9" />

Ja vielä idempotentin testaus:

<img width="533" height="263" alt="Screenshot 2025-10-31 at 10 29 27" src="https://github.com/user-attachments/assets/c929cd09-dbb1-4081-a186-7c06719aaf75" />

Kaikki hyvin!

## b) Toppping

Tein *top-filen*:

<img width="338" height="44" alt="Screenshot 2025-10-31 at 11 38 20" src="https://github.com/user-attachments/assets/2bca9787-2c12-454d-bd92-a0c90139cae2" />

## c) Viisikko tiedostossa

***File*** on tehtynä jo "Hello world" esimerkissä.

***pkg*** on valmiina, kun tein tunnilla esimerkkiä seuraten httpie asennuksen.

***service*** toteutin Apache2 toiminnan varmistuksen YAMLilla init.sls tiedostoon:

<img width="229" height="65" alt="Screenshot 2025-10-31 at 13 32 38" src="https://github.com/user-attachments/assets/917c5e10-2afd-42e5-b893-da11f2c54210" />

***user*** tein samaan tapaan:

<img width="166" height="63" alt="Screenshot 2025-10-31 at 13 45 09" src="https://github.com/user-attachments/assets/5c38b55e-ad13-40cc-b955-10a01263fa56" />

***cmd*** 

---Ongelma---

Ääkkösten käyttö init.sls tiedostossa sai minut etsimään tapaa, jolla muuntaisin systeemini käyttämään UTF-8. Huomasin myös, että UTF-8 ei ole nanollakaan käytössä. ***localella*** varmistin UTF-8 olevan kuitenkin muuten käytössä. 

Sukellus oli liian syvä, enkä saanut vastausta. Teen jotain yksinkertaisempaa.

---Ongelma---

<img width="505" height="67" alt="Screenshot 2025-10-31 at 14 31 50" src="https://github.com/user-attachments/assets/08b39d58-2aa4-426e-b48c-bbef43981b21" />

## d)

En saanut *top.sls* tiedoston kaveriksi toimimaan toista *.sls* tiedostoa, joten laitoin vain ***topin*** ajamaan kahta tilaa:

<img width="504" height="433" alt="Screenshot 2025-11-02 at 14 25 33" src="https://github.com/user-attachments/assets/75c35e81-d731-4a2f-bd50-ca2ed001321d" />

Ja siinä tuleekin samalla todennettua idempotenttius, koska olin jo ajanut nuo ne tehdessäni.


## Lähteet

Karvinen 2014, https://terokarvinen.com/2024/hello-salt-infra-as-code/

Salt Project, https://docs.saltproject.io/salt/user-guide/en/latest/topics/overview.html#rules-of-yaml

Salt Project, https://docs.saltproject.io/en/latest/ref/states/top.html

