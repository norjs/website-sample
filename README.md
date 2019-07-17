# website-sample

Our website source code.

This code has been published as a sample for outside contractors as part of a quote process to create new website for us.

### Tuotanto- ja kehitysversio

 1. Tuotantoversio
     * Git-repository: https://github.com/norjs/m2m.center
     * Web-osoite: https://m2m.center
 2. Kehitysversio
     * Git-repository: https://github.com/norjs/m2m.center-dev
     * Web-osoite: https://dev.m2m.center

#### Github Pages, Jekyll ja Liquid

Nämä sivut on toteutettu staattisesti hostattulle [Github Pages -alustalle](https://pages.github.com/). Githubin 
käyttämä sivustomoottori on nimeltään [Jekyll](https://jekyllrb.com/) ja sitä configuroidaan YML-, HTML- 
JSON-tiedostoilla. 

HTML-tiedostot ovat [Liquid -template-kielellä](https://shopify.github.io/liquid/basics/introduction/).

Tiedostojen alussa voidaan asettaa asetuksia erikoislohkolla (katso [Front Matter](https://jekyllrb.com/docs/front-matter/)).

Sivuston web-osoite päivittyy siirtämällä `git push` -komennolla muutokset master-haarasta Githubiin. Muutokset muissa 
haaroissa eivät päivity minnekään automaattisesti.

### Paikallisen kehitysympäristön asennus

#### Mac OSX -asennus

Asennus: 

```
cd ./docs
npm install
```

Käynnistys: 

```
cd ./docs
npm start
```

#### Windows asennus

 * [Windows asennus](https://jekyllrb.com/docs/installation/windows/) 

##### `./docs/_data/` ja `./docs/_data/lang/LANG.json`

Näissä hakemistoissa on sivuston käyttämä sisältö ja translaatiot. 

Katso [Data Files](https://jekyllrb.com/docs/datafiles/). 

##### `./docs/_layouts`

Sivujen käyttämät [ulkoasut](https://jekyllrb.com/docs/layouts/) löytyvät tästä hakemistosta. 

 * `./docs/_layouts/default.html` -- Tämä on pohja-ulkoasu, jossa on HTML HEAD, preloaderi ja skriptit.
 * `./docs/_layouts/index.html` -- Tämä on verkkosivujen etusivun ulkoasu, joka käyttää default-ulkoasua
 * `./docs/_layouts/page.html` -- Tämä on verkkosivujen tavallisen sivun ulkoasu, joka käyttää default-ulkoasua
 * `./docs/_layouts/post.html` -- Tämä on verkkosivujen blogisivun ulkoasu, joka käyttää page-ulkoasua
 
##### `./docs/_includes/`

Tässä hakemistossa on kaikki sivuston [includoitavat palaset](https://jekyllrb.com/docs/includes/). 

 * `./docs/_includes/common/` - Täällä sijaitsee yleiskäyttöiset leiskan palaset
 * `./docs/_includes/layouts/` - Layouttien tarvitsemat lohkot tulee asettaa tänne
 * `./docs/_includes/pages/LANG/` - Sivujen käyttämät markdown-palaset tulee asettaa tämän alle.

##### `./docs` ja juuressa olevat MD-tiedostot

Kaikki juuressa olevat md-päätteiset tiedostot vastaavat vastaavaa html-tiedostoa valmiilla sivustolla. 

Esimerkiksi:

 * `./docs/index.md` on https://dev.m2m.center/index.html
 * `./docs/m2m-tablet.md` on https://dev.m2m.center/m2m-tablet.html

Tiedoston alussa määritellään mitä teemaa sivu käyttää ja mahdollisesti muita asetuksia.

##### `./docs/posts/`

Tässä hakemistossa sijaitsee kaikki sivuston [blogin artikkelit](https://jekyllrb.com/docs/posts/). 

Aseta tiedoston nimeksi aina `YYYY-MM-DD-otsikon-tag.md`.

##### `./docs/css/`

Tyylitiedostot sijaitsevat tässä hakemistossa.

##### `./docs/images/`

Täällä on sivuston käyttämiä kuvia esimerkiksi artikkeleihin.

##### `./docs/img/`

Tässä hakemistossa on sivuston yleisesti käyttämiä, esim. teeman ja ulkoasun käyttämiä kuvia.

##### `./docs/js/`

Sivuston omat JavaScript-tiedostot menevät tänne.

##### `./docs/lib/`

Ulkopuoliset kirjastot menevät tänne.

### Sivuston leiska

Leiskan on tehnyt alunperin Digiassistentti valmiista templatesta, ja sanoivat 
heillä olleen maksullinen multisite-lisenssi, joten leiskaa kuulemma sai 
muokata poistamalla alkuperäisen tekijän linkin.

Alkuperäinen leiska on tämä: https://bootstrapmade.com/demo/themes/eBusiness/

### Ikonit

Sivustolla voi käyttää joko:

 1. [Font-Awesome v4.7](https://fontawesome.com/v4.7.0/icons/) -ikoneita, tai
 2. [Noun Project](https://thenounproject.com/) -ikoneita (meillä on lisenssi, pyydä tarvittaessa ikoneita)
