---
name: Tukki -tikettijärjestelmä (fi)
layout: page
tools: [Angular, TypeScript, HTML, Sass, Jasmine, REST]
image: assets/images/tukki/lista.png
description: Web-sovellus opettajien ja oppilaiden väliseen kommunikaatioon.
# external_url: github.com/nkahe/Tukki-frontend
---

# Tukki -tikettijärjestelmän frontend

[View this document in English](2-tukki-en.html)

Esittelen tässä *Digivertaisverkko* -hankeessa toteutettua Tukki -tikettijärjestelmän
frontendiä, jota olin toteuttamassa. Tein sitä 14 kk aikana. Frontend on toteutettu [Angularilla](https://angular.io/){:target="_blank" rel="noopener noreferrer"},
ohjelmointikielenä oli Typescript ja tyylimäärittelyissä Sass/SCSS. Reaktiivisuuden käsittelyssä hyödynsin tarvittaessa RxJS -kirjastoa perinteisten promiseiden ohella.
[voi lukea täältä.](https://github.com/nkahe/Tukki-frontend/blob/main/documentation/kuvaus/kuvaus.md){:target="_blank" rel="noopener noreferrer"}
Siinä on eritelty tarkemmin käytettyjä tekniikoita ja sovelluksen arkkitehtuuria. Sovelluksen backend käyttää Node.JS:ää, tietokantana PostreSQL:ää ja kommunikointi frontendin kanssa tapahtuu REST API:n kautta. Tekstieditorina käytin VS Codea.

Sovelluksen lähdekoodi on avointa ja [nähtävillä Githubissa -repossani](http://github.com/nkahe/Tukki-frontend){:target="_blank" rel="noopener noreferrer"}.

## Sovelluksen kuvaus

Sovellus on tarkoitettu helpottamaan korkeakouluissa ohjelmointia opettavien opettajien ja opiskelijoille välistä kommunikaatiota. Sovelluksella opiskelijat voivat esittää kurssin opettajille kysymyksiä, ja opettajat voivat vastata näihin lisäämällä kysymyksiin kommentteja.

Tekniseen tiimiin kuului minun lisäksi kaksi tiimiläistä. Keskityin seuraaviin osa-alueisiin front-endissä:

- Frontend-arkkitehtuuri
- Suuren osan toteutuksesta
- Tekninen dokumentaatio
- Lähes kaikki yksikkötestit

Muiden tiimiläisteni tekemää:

- Sovelluksen toiminnallisuus- ja käyttöliittymäsuunnittelu
- Osia frontendista: Rich text editori, UKK:n tekeminen kysymyksestä,
profiilinäkymä, kysymysnäkymien lisäkentät, tietosuojaselosteen sisältö.

Projektin (front-endin) lähdekoodin koko numeroina:

| Kieli        | Tiedostot | Tyhjiä | Kommentteja | Koodia  |
| ------------ | --------- | ------ | ----------- | ------- |
| TypeScript   | 123       | 1508   | 1854        | 10660   |
| HTML         | 27        | 510    | 74          | 3179    |
| SCSS         | 38        | 376    | 136         | 1766    |
| JSON         | 2         | 0      | 0           | 319     |
| **Yhteensä** | 190       | 2394   | 2064        | 15924   |


## Toteutuksen esittely

En käy läpi kaikkia järjestelmän toimintoja tai näkymiä, mutta esittelen joitain poimintoja. Sovellus on suunniteltu käytettäväksi ensisijaisesti tietokoneen näytöltä tai tablettikoosta, mutta on käytettävissä myös puhelinkoossa. Saavutettavuuteen on kiinnitetty huomiota.

Kysymysten listaus on sovelluksen päänäkymä:

![kysymyslista](assets/images/tukki/lista.png)

Sovellus on upotettavissa Moodle -oppimisjärjestelmään, tai sitä voidaan käyttää itsenäisenä verkkosovelluksena. Yllä on jälkimmäinen näkymä. Opettajana kirjautuneena näkyvät kaikki kurssin opettajille esitetyt kysymykset. Oppilaalle näkyvät vain kaikki hänen lähettämänsä kysymykset. Kaikille ovat nähtävillä lisäksi opettajien kurssille lähettämät *Usein kysytyt kysymykset* (jatkossa UKK). 

Taulukko, kuten suurin osa sovelluksen komponenteista, on tehty Angular Material -kirjastoa hyödyntäen, jonka ulkonäköä on tarvittaessa muokattu. Osan komponenteissa olen tehnyt itse. Taulukon rivit voi järjestää eri sarakkeiden mukaan ja niitä voi suodattaa eri kysymysten sisältämien tietojen mukaan. Taulukon sisältö päivittyy minuutin välein tai manuaalisesti.

![kysymyslista](assets/images/tukki/lista-en.png)

![kysymyslista](assets/images/tukki/valikko.png)

Sovelluksessa käytetyn kielen voi vaihtaa englanniksi. Tein tekstin käännökset. Käyttäjät voivat tarkastella käyttäjäprofiiliaan ja opettajat voivat muokata kurssin asetuksia.

![kysymyslista](assets/images/tukki/login.png)

Moodleen upotettuna kirjautumistieto saadaan sieltä. Sen ulkopuolella käytettynä kirjautuminen tehdään ensin manuaalisesti tunnuksella ja salasanalla. Kirjautumisessa käytetään monivaiheista <i>authorization code flow</i>:a. Sen jälkeen tunnistautuminen tapahtuu saadulla keksillä.

![uusi kysymys](assets/images/tukki/tiketti.png)

Yksittäisen kysymyksen näkymässä käyttäjä voi tarkastella kysymyksen tietoja.
Opettaja voi kopioi kysymyksen UKK:ksi tai asettaa sen tilan ratkaistuksi. Kysymyksen lähettäjä voi poistaa tai muokata kysymystä. Opettajat ja opiskelija voivat lisätä
kysymykseen kommentteja, jotka näkyvät kysymyksen alla. Käyttäjät voivat muokata
omia kommenttejaan.

![kommentti](assets/images/tukki/kommentti.png)

Kysymyksen ja kommentin yhteydessä näkyy lähettäjän nimi, rooli, avatar-ikoni ja
kommentin lähettämis- ja muokkaamispäivämäärä. Tein tämän komponentin itse. Kommenttia muokatessa sen voi poistaa, muuttaa kommentin tai tekstin tilaa sekä
lisätä tai poistaa liitteitä. Tein liitteiden näkymä- ja lähettämiskomponentit itse.

![kommentti](assets/images/tukki/progress-bar.png)

Tiedostoja voi lisätä useita, ne lähetetään rinnakkain ja niiden lähetyksen tila
päivitetään edistymispalkeilla, ja niiden lähettäminen voidaan halutessa keskeyttää.

![oletko varma](assets/images/tukki/oletko-varma.png)

Uuden UKK:n lisäämisen näkymä. Tässä käyttäjä on painanut "Alkuun" -nappi kesken muokkauksen, jolloin kysytään varmistusta. Lomakkeiden validointiin on käytetty *Angular Reactive Forms*:a.

![asetukset](assets/images/tukki/asetukset.png)

Kurssilla olevata opettajat voivat muuttaa kurssin asetuksia, ladata ja lisätä
usein kysyttyjä kysymyksiä sekä kurssin asetuksiax JSON -tiedostoina seka kutsua ulkopuolisia osallistumaan kurssille. Lisäkenttien editointi-ikonia valitsemalla avautuu
niiden muokkausnäkymä (alla).

![asetukset](assets/images/tukki/lisäkenttä.png)

Lisäkenttien muokkausnäkymä. Monivalintojen lisääminen on toteutettu Angular
Materialin chipseillä.


{% include elements/button.html link="#" text="Takaisin alkuun" block=true %}
