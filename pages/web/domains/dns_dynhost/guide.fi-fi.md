---
<<<<<<< HEAD
title: 'Dynaamisen nimipalvelimen määrittäminen verkkotunnukselle'
slug: webhotelli_dynhost
excerpt: 'Opi määrittämään dynaaminen DNS-tietue (DynHost) OVH:n verkkotunnuksellesi'
section: 'DNS ja DNS-alue'
order: 6
---

**Päivitetty 20.7.2018**

## Tavoite

Verkkotunnuksen Domain Name System (DNS) -alue sisältää sen konfigurointitiedoston. Tämä koostuu teknisistä tiedoista, joita kutsutaan tietueiksi. DNS-tietueen päivittäminen dynaamisesti voi osoittautua välttämättömäksi pidentyneen palvelukatkoksen välttämiseksi. Tähän voi olla erilaisia syitä, kuten oman pelipalvelimen ylläpito ilman ”kiinteää” IP-osoitetta. 

**Opi määrittämään dynaaminen DNS-tietue (DynHost) OVH:n verkkotunnuksellesi.**

## Edellytykset

- Sinulla on pääsyoikeus verkkotunnuksen hallintaan [OVH:n hallintapaneelissa](https://www.ovh.com/auth/?action=gotomanager){.external}.
- Käytät kyseistä verkkotunnusta varten OVH:n konfiguraatiota (nimipalvelimia).
- DynHost-tietue, jonka luomiseen valmistaudut, ei saa olla olemassa verkkotunnuksesi DNS-alueella “A”-tietueena.

> [!warning]
>
> - Jos verkkotunnuksesi ei käytä OVH:n nimipalvelimia, sinun on lähestyttävä sen konfiguraatiota hallinnoivaa palveluntarjoajaa seuraavaa vaihetta varten.
> 
> - Jos verkkotunnuksesi on rekisteröity OVH:lle, voit tarkistaa, käyttääkö se konfiguraatiotamme. Mene sitä varten [hallintapaneelin](https://www.ovh.com/auth/?action=gotomanager){.external} välilehdelle `Nimipalvelimet`{.action}, kun olet ensin siirtynyt kyseiseen verkkotunnukseen.
>

## Käytännössä

### 1. vaihe: DynHost-käyttäjän luominen

Ensimmäinen vaihe koostuu DynHost-käyttäjän luomisesta. Tämän avulla voit toteuttaa dynaamisen DNS-tietueen päivityksen, jonka haluat luoda. Menettelyn aloittamiseksi kirjaudu [hallintapaneeliisi](https://www.ovh.com/auth/?action=gotomanager){.external}, klikkaa `Verkkotunnukset`{.action} vasemman reunan valikossa ja valitse sitten kyseessä oleva verkkotunnus. Mene lopuksi välilehdelle `Sähköpostit`{.action}.

![dynhost](images/use-dynhost-step1.png){.thumbnail}

Klikkaa sitten painiketta `Yhteyksien hallinta`{.action} ja sitten `Luo tunnus`{.action}. Täydennä avautuvassa ikkunassa pyydetyt tiedot:

|Tiedot|Kuvaus|
|---|---|
|Tunnuksen pääte|Määritä pääte DynHost-tunnukselle, jota olet luomassa.|
|Aliverkkotunnus|Määritä aliverkkotunnus, jota dynaamisen DNS-tietueen luominen koskee.|
|Salasana|Määritä salasana DynHost-tunnukselle ja vahvista se.|

Kun kentät on täytetty, klikkaa painiketta `Vahvista`{.action}. Tunnus on nyt näkyvissä nykyisen sivun taulukossa. Toista tämä vaihe niin monta kertaa kuin tarvitset, jos kaipaat ylimääräisiä DynHost-tunnuksia.

![dynhost](images/use-dynhost-step2.png){.thumbnail}

### 2. vaihe: Luo dynaaminen DNS-tietue (DynHost)

Toisessa vaiheessa luodaan DNS-tietue, joka on päivitettävä dynaamisesti. Muistathan, että sitä ei saa olla jo olemassa OVH:n verkkotunnuksesi DNS-alueella “A”-tietueena. Sen tarkistamista ja tarvittaessa poistamista varten voit katsoa dokumentaatiotamme “[OVH:n DNS-alueen muokkaus](https://docs.ovh.com/fi/domains/miten_dns-aluetta_muokataan/){.external}”.

Kun olet valmis luomaan DynHost-tietueen, mene uudelleen `DynHost`{.action}-välilehden etusivulle ja klikkaa painiketta `Lisää DynHost`{.action}. Täydennä avautuvassa ikkunassa pyydetyt tiedot:

|Tiedot|Kuvaus|
|---|---|
|Aliverkkotunnus|Syötä aliverkkotunnus, jonka DNS-tietue on päivitettävä dynaamisesti. Tämän aliverkkotunnuksen on vastattava DynHost-käyttäjän luomisen yhteydessä annettua aliverkkotunnusta.|
|Kohde IP-osoite|Syötä IP-osoite, jota DNS-tietueen on nyt käytettävä. DynHostin periaatteen mukaisesti se päivitetään seuraavaksi.|

Kun kentät on täytetty, klikkaa painiketta `Vahvista`{.action}. DynHost-tietue on nyt näkyvissä nykyisen sivun taulukossa. Toista tämä vaihe niin monta kertaa kuin tarvitset, jos kaipaat ylimääräisiä DynHost-tietueita.

![dynhost](images/use-dynhost-step3.png){.thumbnail}

### 3. vaihe: DynHost-muutoksen automatisointi

Nyt kun käyttäjä ja DynHost-tietue on luotu, on viimeisessä vaiheessa automatisoitava DNS-tietueen päivitys, jotta se tapahtuu dynaamisesti. Tätä varten täytyy käyttää asiakasohjelmaa, joka tarkistaa säännöllisesti kohde IP -osoitteen ja päivittää sen, mikäli se on muuttunut.

> [!warning]
>
> Asiakasohjelman asennus ja konfigurointi täytyy toteuttaa oman osaamisesi mukaan. Joitakin menettelyä koskevia tietoja on esitelty alla. Suosittelemme ottamaan kuitenkin yhteyttä erikoistuneeseen palveluntarjoajaan, mikäli kohtaat hankaluuksia. Me emme siis voi tarjota avustusta asiassa. 
>

Koska mahdollisuudet ovat laajat, kannattaa muistaa, että tämä asiakasohjelma voidaan asentaa palvelimellesi tai tietokoneellesi. Se voi olla myös jo saatavilla reitittimesi käyttöliittymässä, mikäli tämä on yhteensopiva. Kun asiakasohjelma on valittu ja asennettu, se on konfiguroitava käyttämällä aiemmin luodun DynHost-käyttäjän tietoja.

Asiakasohjelmasta riippuen on mahdollista, että DynHost-käyttäjän elementtien sekä kyseessä olevan aliverkkotunnuksen lisäksi vaaditaan myös päivityksen URL. Jos näin on, käytä alla olevaa URL-osoitetta ja korvaa huolellisesti siinä olevat yleiset tiedot:

http://www.ovh.com/nic/update?system=dyndns&hostname=**$HOSTNAME**&myip=**$IP**

|Tiedot|Korvaava tieto|
|---|---|
|$HOSTNAME|Aliverkkotunnus, jota muokkaus koskee.|
|$IP|Uusi kohde IP -osoite.|

Voit tarkistaa hallintapaneelisi `DynHost`{.action}-välilehdeltä, että IP-osoite on varmasti päivittynyt. Tarkista IP-osoite, joka näkyy sarakkeessa `Kohde`{.action}.

![dynhost](images/use-dynhost-step4.png){.thumbnail}

## Lue lisää aiheesta

=======
title: 'OVH:n DNS-alueen luominen verkkotunnukselle'
slug: webhotelli_dynhost
excerpt: 'Opi luomaan DNS-alue verkkotunnuksellesi hallintapaneelisi kautta OVH:lla'
section: 'DNS ja DNS-alue'
order: 2
---

**Päivitetty 05.7.2018**

## Tavoite

Verkkotunnuksen Domain Name System (DNS) -alue muodostaa sen konfigurointitiedoston. Se koostuu teknisistä tiedoista, joita kutsutaan tietueiksi. Perinteisessä käytössä näillä tietueilla voidaan yhdistää verkkotunnuksesi ja palvelin tai palvelimet, jotka ylläpitävät verkkosivuasi ja sähköpostiosoitteitasi.

On erilaisia syitä, joiden vuoksi saatat joutua luomaan DNS-alueen verkkotunnuksellesi OVH:lla.

**Opi luomaan DNS-alue verkkotunnuksellesi hallintapaneelisi kautta OVH:lla.**

## Edellytykset

- Sinulla on verkkotunnus.
- Kyseisellä verkkotunnuksella ei ole ennestään OVH:n DNS-aluetta eikä sillä ole meneillään toimenpidettä tai tilausta OVH:lla.
- Verkkotunnuksen tekninen konfigurointi on oikein (tila, SOA jne.).
- Olet kirjautunut [hallintapaneeliin](https://www.ovh.com/auth/?action=gotomanager){.external}.

## Käytännössä

### 1. vaihe: DNS-alueen luominen hallintapaneelissa

Kirjaudu [hallintapaneeliisi](https://www.ovh.com/auth/?action=gotomanager){.external}, klikkaa `Tilaa`{.action} vasemman reunan valikossa ja sitten `DNS-alue`{.action}.

Syötä näkyviin tulevalle sivulle verkkotunnus, jolle haluat luoda DNS-alueen. Odota hetki, että työkalu suorittaa verkkotunnusta koskevat tarkistukset.

Jos näkyviin ilmestyvä viesti ilmoittaa, ettei DNS-aluetta voida luoda, tarkista, että verkkotunnus noudattaa vaadittuja ennakkoedellytyksiä tai pyydä verkkotunnusta hallinnoivaa henkilöä tekemään tämä tarkistus. Kun kaikki on oikein, yritä menettelyä uudestaan.

![dnszonecreate](images/dns-zone-create-step1.png){.thumbnail}

Kun tarkastus on tehty, sinun on valittava aktivoitko vähimmäistietueet DNS-alueelle, jota olet luomassa. Valinta ei ole lopullinen, sillä voit muokata tietueita DNS-alueen luomisen jälkeen.

|Aktivoitko vähimmäistietueet?|Yksityiskohdat|
|---|---|
|Kyllä|Valitse tämä, jos haluat jatkossa personoida DNS-aluetta itse.|
|Ei|Valitse tämä, jos tarkoituksesi on käyttää OVH:n palveluja kuten [webhotellia](https://www.ovh-hosting.fi/webhotelli/){.external}, joissa alue on esikonfiguroitu.|

![dnszonecreate](images/dns-zone-create-step2.png){.thumbnail}

Kun olet tehnyt valintasi, seuraa vaiheita DNS-alueen luomiseen saakka.

### 2. vaihe: DNS-alueen muokkaus (valinnainen)

Kun verkkotunnuksesi DNS-alue on luotu, voit muokata sitä. Tämä toimenpide on valinnainen, mutta se voi olla välttämätön, jos haluat varmistua verkkotunnukseen liitettyjen palveluidesi (kuten verkkosivujen ja sähköpostiosoitteiden) käytettävyydestä.

Jos haluat muokata DNS-aluetta [hallintapaneelissa](https://www.ovh.com/auth/?action=gotomanager){.external}, klikkaa kohtaa `Verkkotunnukset`{.action} vasemman reunan valikossa ja valitse sitten kyseessä oleva verkkotunnus. Mene lopuksi välilehdelle `DNS-alue`{.action}.

> [!primary]
>
> Jos olet juuri luonut DNS-alueen eikä verkkotunnustasi näy vielä `Verkkotunnusten`{.action} palvelulistassasi, odota hetki ja lataa sitten sivu uudelleen.
>

Tee tämän jälkeen tarvittavat toimenpiteet. Voit lukea lisää DNS-alueen muokkauksesta dokumentaatiostamme [“OVH:n DNS-alueen muokkaus”](https://docs.ovh.com/fi/domains/miten_dns-aluetta_muokataan/){.external}. Kun verkkotunnuksesi OVH:n DNS-aluetta on muokattu, tarvitaan enintään 4-24 tuntia kestävä propagaatioaika, jotta muutokset astuvat voimaan.

### 3. vaihe: OVH:n verkkotunnuksen nimipalvelinten muokkaus

Kun DNS-alue OVH:lla on valmis käytettäväksi, sinun on liitettävä siihen verkkotunnuksesi. Hae sitä varten etukäteen verkkotunnustasi varten aktivoidut nimipalvelimet hallintapaneelista. Nämä näkyvät kohdan `Name Servers`{.action} alla.

![dnszonecreate](images/dns-zone-create-step3.png){.thumbnail}

Kun sinulla on verkkotunnuksesi nimipalvelimet, **muokkaa nimipalvelimia verkkotunnustasi hallinnoivan palveluntarjoajan käyttöliittymässä**. Kun toimenpide on tehty, tarvitaan enintään 48 tunnin propagaatioaika ennen kuin muutos on astunut voimaan.

## Lue lisää aiheesta

[Miten DNS-aluetta muokataan?](https://docs.ovh.com/fi/domains/miten_dns-aluetta_muokataan/){.external}

>>>>>>> FR_update_plugin-ovh-network
Viesti käyttäjäyhteisömme kanssa osoitteessa: <https://community.ovh.com/en/>.