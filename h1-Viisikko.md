# h1 Viisikko

a) Debian 12 Macille asennettu ohjeiden mukaan toimimaan UTM:n kautta. Hommia helpottamaan löytyi mac näppäimistövalinta!

b) Saltin asentamisessa ei ongelmaa! 

c) 
## pkg.
Sain komennolla <em>sudo salt-call --local -l info state.single pkg.installed tree</em> odotetun tuloksen:

<img width="539" height="267" alt="Screenshot 2025-10-24 at 15 26 40" src="https://github.com/user-attachments/assets/7537672b-e748-47a8-adea-1f31f93160fd" />

...jossa kerrotaan minun asentaneen jo treen.

## file
Loin komennolla <em>sudo salt-call --local -l info state.single file.managed /tmp/moikkaniilo</em> tmp -kansioon moikkaniillo -nimisen tiedoston, johon lisäsin vielä viestin "Lol" komennolla <em>sudo salt-call --local -l info state.single file.managed /tmp/moikkaniilo contents="Lol"</em>. <br>
<img width="440" height="320" alt="Screenshot 2025-10-24 at 15 32 38" src="https://github.com/user-attachments/assets/82fca7c1-e145-4674-b8ee-328a120bab29" />
<img width="408" height="383" alt="Screenshot 2025-10-24 at 15 33 28" src="https://github.com/user-attachments/assets/2f499fd9-39a7-4222-b783-f81e785c2620" />

## service
Varmistin <em>sudo salt-call --local -l info state.single service.running apache2 enable=True</em> -komennolla apcachen olevan sekä käynnissä että aina valmiina päällä koneen käynnistyessä. <br>
<img width="478" height="262" alt="Screenshot 2025-10-24 at 16 03 13" src="https://github.com/user-attachments/assets/9942cf74-71e5-479e-a99f-4e95b0e78a82" />

## user
Komennolla <em>sudo salt-call --local -l info state.single user.present niilo89</em> tarkistutin, ja sittemmin loin uuden käyttäjän niilo89. <br>
<img width="357" height="685" alt="Screenshot 2025-10-24 at 16 10 02" src="https://github.com/user-attachments/assets/97a550e7-f1f3-46ae-9416-f4e2747ea99f" />

## cmd
Tein komennolla <em>sudo salt-call --local -l info state.single cmd.run 'touch /tmp/foo' creates="/tmp/foo"</em> foo -nimisen tiedoston. Tarkastutin sen onnistumisen, sekä idempotenssin toimimisen, ajamalla saman komennon uudelleen ja kaikkihan toimi: <br>
<img width="277" height="263" alt="Screenshot 2025-10-24 at 16 26 33" src="https://github.com/user-attachments/assets/8fa4d132-15f4-4574-a3f8-8aa59d89b872" />

d) Tämä tulikin hienosti esille viimeistään cmd.run -osassa. Ajo suoritti luonnin ainoastaan, jos tiedostoa ei ollut. Ilman creates -lisäkomentoa tiedosto olisi aina päivittynyt ja tästä olisi tullut aina muutosilmoitus raporttiin. User -kohdassa ajo myös tarkasti ensin käyttäjän olemassaolon ja sitten vasta tarvittaessa loi sen.


## Lähteet
Debianin ja UTM:n asennus:<br>
[New Mac M1 notes Marcus Carr (2024), with Debian 12-Bookworm](https://github.com/MarcCarr/InfoSecMC/blob/main/H2_Kill_Chain.md#a-bookworm) <br>
Saltin asennus:<br>
[Install Salt on Debian 13 Trixie](https://terokarvinen.com/install-salt-on-debian-13-trixie/)<br>
Run Salt Command Locally:<br>
https://terokarvinen.com/2021/salt-run-command-locally/<br>

