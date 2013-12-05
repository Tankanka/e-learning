##JOHDANTO

Metropolia ammattikorkeakoululla on käytössä Kana -sisätilapaikannusjärjestelmä. Sen toiminta perustuu laitteiden lähettämään signaaliin, kun niissä on wifi päällä. Järjestelmän avulla voidaan nähdä missä luokkatilassa tai muussa tilassa järjestelmään kirjautuneet henkilöt kyseisellä hetkellä ovat.

"Ohjelmistotuotanto" -kurssin projektityönä on ideoida uusia sovelluksia, jotka hyödyntävät Kana -sisätilapaikannusjärjestelmää. Ideoimamme järjestelmän avulla opiskelija voi kirjautua luennolle läsnäolevaksi ollessaan oikeaan aikaa oikeassa paikassa. Jos opiskelijalla ei ole puhelinta/tablettia mukana luennolla, voi opettaja kirjata hänet tunnille läsnäolevaksi manuaalisesti. Tämän lisäksi ohjelman avulla opiskelija tai opettaja voivat lähettää tiedostoja luennolla länäoleville.

Ideoimamme sovellus on ensimmäinen versio opetuksen apuna käytettävästä mobiilisovelluksesta. Tämän päälle on mahdollista rakentaa lisäominaisuuksia myöhemmin.


##Käyttötapaukset

Opiskelijan käyttötapaukset:

- opiskelija voi kirjautua läsnäolevaksi tunnille
- opiskelija voi katsoa ohjelmasta kuinka monella tunnilla on ollut paikalla
- opiskelija voi palauttaa luentotehtävän opettajalle sähköisesti
- opiskelija voi jakaa kaikille tunnilla läsnäoleville tiedoston
- opiskelija voi joko hyväksyä tai hylätä opettajan/toisen opiskelijan lähettämän tiedoston


Opettajan käyttötapaukset:

- opettaja voi kirjata opiskelijan läsnäolevaksi tunnille, jos opiskelijalla ei ole puhelinta/tablettia mukana
- opettaja voi lähettää sähköisesti tiedostoja läsnäolevien opiskelijoiden puhelimiin/tabletteihin
- opettaja voi hyväksyä tai hylätä opiskelijan lähettämän tiedoston
- opettaja näkee kuinka monella tunnilla kukin opiskelija on ollut paikalla
- opettaja voi korjata läsnä-/poissaoloja myöhemmin ohjelmasta
- opettaja voi päättää riittävän läsnäoloajan/luentokerta läsnäolomerkinnän vaatimiseksi

##Käyttäjäryhmien määrittely

- Opettajat: Luentojen vetäjä, joka vastaa luennosta
- Opiskelijat: Luennoille osallistuvat henkilöt, jotka ovat suorittamassa kyseistä kurssia

##Käyttötapauskaavio(t)
![kayttotapauskaavio](http://users.metropolia.fi/~tarjajar/ohtu/kayttotapaukset.jpg)

##Käyttäjäskenaario

Opiskelija on menossa luennolle ja haluaa kirjautua luennolle läsnäolevaksi.

![vuokaavio](http://users.metropolia.fi/~tarjajar/ohtu/vuokaavio2.jpg)


## Järjestelmäarkkitehtuuri

- Opiskelijan/opettajan laite ottaa yhteyden wifi-yhteyspisteeseen
- Wifi-yhteyspisteestä signaali siirtyy palvelimelle

![jarjestelmaarkkitehtuuri](http://users.metropolia.fi/~joonasee/github-tehtavat/Jarjestelmaarkkitehtuuri.jpg)



##Funktionaaliset vaatimukset

- Opiskelijan täytyy pystyä kirjautumaan läsnäolevaksi kurssille
- Opiskelijan täytyy pystyä tarkastelemaan omia läsnäolomääriä kurssilla
- Opiskelijan täytyy pystyä lähettämään muille läsnäolijoille tiedostoja
- Opiskelijan täytyy pystyä vastaanottamaan tiedostoja opettajalta tai muilta läsnäolijoilta
- Opettajan täytyy pystyä kirjaamaan opiskelija läsnäolevaksi luennolle
- Opettajan täytyy pystyä lähettämään tiedostoja läsnäolijoille
- Opettajan täytyy pystyä vastaanottamaan tiedostoja läsnäolijoilta

##Ei-funktionaaliset järjestelmävaatimukset

- Opiskelijalla tulee olla käytössä älypuhelin tai tabletti, jossa wifi-yhteys. Opettajalla tulee olla käytössä älypuhelin tai tabletti, jolla voi kirjata opiskelija manuaalisesti läsnäolevaksi kurssille.
- Puhelimessa oltava käyttöjärjestelmä, joka tukee sovellusta. Tällä hetkellä sovellus tukee Android-, iOS- ja Windows Phone -käyttöjärjestelmiä.
- Koulun wifi-yhteydet: oltava runsaasti ja osattava sovellusten kautta paikantaa oppilas. Oikean wifi-yhteyden luona mahdollista rekisteröidä itsensä tunnille.
- Wifi-yhteyden oltava jatkuvasti päällä tiedostonsiirtoa ja tiedostojen palautusta varten. Sovellus keskeyttää toimimisen ja yrittää muodostaa yhteyden heti, kun huomaa yhteysvirheen.
- Vahva wifi-signaali on tärkeä, kun lähetetään tiedostoja monelle henkilölle samaan aikaan.
- Sovelluksen tulee toimia matalatehoisellakin älypuhelimella
- Wifi-paikannuksen tulee olla tarkka, jotta opiskelija ei voi esimerkiksi kahvilasta kirjautua luennolle, joka järjestetään kolmannessa kerroksessa.



Käyttöliittymä
==============
Järjestelmä koostuu viidestä (5) päänäkymästä
- Sisäänkirjautuminen
- Etusivu
- Kurssit
- Yksittäinen kurssinäkymä
- Opettajan yksittäinen kurssinäkymä

Siirtymät näkymien välillä

![siirtyma](http://users.metropolia.fi/~tarjajar/ohtu/siirtyma.jpg)

Sisäänkirjautumissivu on sekä opettajille, että oppilaille samannäköinen.

![sisaankirjautuminen](http://users.metropolia.fi/~joonasee/github-tehtavat/sisaankirjautuminen.jpg)

Sisäänkirjautumissivulta järjestelmä menee automaattisesti Etusivulle, josta käyttäjä näkee kyseisen päivän lukujärjestyksensä. Järjestelmä on synkronoitu Tuubin ja Lukkarikoneen kanssa. Kurssin nimeä painamalla käyttäjä pääsee kyseisen kurssin omalle sivulle.

![etusivu](http://users.metropolia.fi/~joonasee/github-tehtavat/Etusivu.jpg)

Kurssit -alasivulta löytyy listauksena kaikki kurssit, joille käyttäjä osallistuu kyseisen jakson aikana. Kurssin nimeä painamalla käyttäjä pääsee kyseisen kurssin omalle sivulle. Kurssin nimen alta löytyy tieto siitä miten monta pakollista läsnäoloa kurssilla on ja miten monta kertaa kyseinen opiskelija on ollut paikalla.

![kurssit](http://users.metropolia.fi/~joonasee/github-tehtavat/Kurssit.jpg)

Yksittäisen kurssin näkymässä opiskelija näkee tarkemmin kurssin läsnäolovaatimukset. Kun luento on alkamassa ja opiskelija on oikeassa luokassa muuttuu "Kirjaudu läsnäolevaksi" -nappi vihreäksi ja opiskelija pystyy kirjautumaan läsnäolevaksi.

![yksittainen](http://users.metropolia.fi/~joonasee/github-tehtavat/Kurssinakyma.jpg)

Opettajan kurssinäkymä poikkeaa hieman oppilaan näkymästä. Opettaja näkee koko ajan päivittyvän prosentin siitä kuinka moni on oppitunnille kirjautunut läsnäolevaksi. Opettaja voi myös manuaalisesti lisätä oppilaan läsnäolevaksi, jos oppilaalle ei ole puhelinta tai tablettia mukana. Opettaja voi myös lähettää tiedostoja kaikille luennolla läsnäoleville.
![opettajan kurssi](http://users.metropolia.fi/~joonasee/github-tehtavat/Opettajan_Kurssinakyma.jpg)

