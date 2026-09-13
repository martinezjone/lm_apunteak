# CSS

CSS3, CSS estandarraren berrikuspenik berriena da eta orriaren **itxura** kontrolatzeko erabiltzen den lengoaia da: koloreak, tipografiak, kokapenak, animazioak eta orriaren egitura bera nola erakusten den zehazten du.

## Zer da CSS?

1. CSSk **Cascading Style Sheets** esan nahi du (kaskada-estilo orriak).
2. HTML dokumentuen **itxura eta maketazioa** definitzeko erabiltzen den lengoaia da.
3. **Ez da** markatze-lengoaia bat, ezta programazio-lengoaia bat ere; **estilo-lengoaia** bat da.
4. "Kaskada" izena du araua batzuk beste batzuei gainjartzen zaizkielako, lehentasun-ordena jakin bati jarraituz.
5. HTMLrekin (edukiarekin) eta JavaScriptekin (interakzioarekin) batera funtzionatzen du.
6. CSS fitxategiek **.css** luzapena dute.


## CSS HTML batean txertatzeko moduak

Hiru modu daude CSSa HTML dokumentu bati lotzeko:

### 1. Elementuari zuzenean (inline)

`style` atributuaren bidez, elementuari zuzenean estiloa jartzen zaio:

```
<p style="color: red; text-align: center;">Testu hau gorriz eta zentratuta agertuko da</p>
```

### 2. `<head>` barruko `<style>` elementuan (internal)

```
<head>
    <style>
        p {
            color: red;
        }
    </style>
</head>
```

### 3. Kanpoko fitxategi baten bidez (external)

Hau da **modu gomendatuena**, HTML kodea txukunago geratzen delako eta CSS berbera hainbat HTML orriren artean birrerabil daitekeelako:

```
<head>
    <link rel="stylesheet" type="text/css" href="css/estiloak.css">
</head>
```

!!! note
    Hiru moduak batera erabiliz gero, gogoratu **lehentasun-ordena**: elementuko `style` atributuak > `<head>`-eko `<style>`-k > kanpoko fitxategiak. 
    Hau da, gatazkarik badago, elementuari zuzenean jarritako estiloak irabaziko du beti.

## Oinarrizko sintaxia

CSS **arauen** bidez funtzionatzen du. Araua osatzen duten hiru osagaiak hauek dira:

```
hautatzailea {
    propietatea: balioa;
    propietatea: balioa;
}
```

| Osagaia | Adibidea | Azalpena |
| --- | --- | --- |
| Hautatzailea (selektorea) | `p` | Zein elementuri eragingo dion adierazten du. |
| Propietatea | `color` | Aldatu nahi den ezaugarria. |
| Balioa | `blue` | Propietateari ezarritako balioa. |
| Deklarazioa | `color: blue;` | Propietatea eta balioa batera, puntu eta komarekin amaituta. |

```
p {
    color: blue;
    font-size: 16px;
}
```

!!! example "Ariketa 1"
    Sintaxi hau praktikatzeko, lehenengo ariketa hau egingo dugu: *(ariketaren esteka hemen gehituko da)*

## Hautatzaileak

Elementuak "hautatzeko" hainbat modu daude. Hauek dira garrantzitsuenak.

### Elementu-hautatzailea

Etiketa-mota bereko elementu **guztiei** eragiten die:

```
p {
    color: blue;
}
```

Koma bidez, hainbat elementu-motari estilo bera eman dakieke:

```
h1, h2, p {
    color: blue;
}
```

### Class hautatzailea: `.class`

`.class="izena"` hautatzaileak zehaztuta dauden elementu guztiak hautatzen ditu. HTML elementu askori class bera jar dakieke:

```
<p class="arrosa">Paragrafo hau arrosa-kolorekoa izango da.</p>
<div class="arrosa">Div hau ere arrosa-kolorekoa izango da.</div>
```

```
.arrosa {
    background-color: pink;
}
```

Elementu-motari lotuta ere erabil daiteke (kasu horretan, elementu mota horretan bakarrik izango du eragina):

```
p.arrosa {
    background-color: pink;
}
```

### Id hautatzailea: `#id`

`#id` hautatzaileak `id` horrekin zehaztuta dagoen elementu **bakarra** hautatzen du. Garrantzitsua da HTML dokumentu batean ez errepikatzea `id` bera bi elementutan:

```
<h1 id="izenburu_nagusia">Titulua</h1>
```

```
#izenburu_nagusia {
    color: blue;
    font-size: 30px;
}
```

| | `.class` | `#id` |
| --- | --- | --- |
| Elementu batean erabiltzeko aldiak | Behin baino gehiagotan (elementu asko) | Behin bakarrik (elementu bat) |
| HTML batean errepika daiteke? | Bai | Ez |

### Hautatzaileen konbinazioak

```
/* Ondorengo (descendant): ul baten barruan dauden li GUZTIAK, 
   zuzeneko seme izan ala ez */
ul li {
    color: blue;
}

/* Ume zuzena (child): ul baten UME ZUZENAK diren li-ak bakarrik */
ul > li {
    color: blue;
}

/* Elkarren ondoko anaia (adjacent sibling): div baten ONDOREN 
   datorren lehen p-a bakarrik */
div + p {
    color: blue;
}
```

### Pseudo-klaseak

Elementu bat egoera berezi batean dagoenean aplikatzen dira:

| Pseudo-klasea | Erabilera |
| --- | --- |
| `a:link` | Oraindik bisitatu gabeko esteka. |
| `a:visited` | Aurretik bisitatutako esteka. |
| `a:hover` | Sagua elementuaren gainean dagoenean. |
| `a:active` | Elementuan klik egiten ari garenean. |
| `input:checked` | Markatutako checkbox/radio bat. |
| `p:first-child` | Elementua bere gurasoaren lehen semea denean. |
| `p:last-child` | Elementua bere gurasoaren azken semea denean. |
| `p:nth-child(2)` | Elementua bere gurasoaren N. semea denean. |

```
a:hover {
    color: red;
    text-decoration: underline;
}
```


!!! example "Ariketa 2"
    Hautatzaileak lantzeko ariketa hau egingo dugu: *(ariketaren esteka hemen gehituko da)*

## Kutxen eredua (Box model)

CSSn **elementu guztiak kutxak** dira. Kutxa bakoitzak lau geruza ditu, kanpotik barrurantz:

1. **Margin** (marjina): kutxaren kanpoko espazioa, beste kutxekiko banaketa.
2. **Border** (ertza): kutxaren muga.
3. **Padding** (betegarria): edukiaren eta ertzaren arteko barruko espazioa.
4. **Content** (edukia): testua, irudia edo beste elementuak.

```
div {
    width: 300px;
    padding: 20px;
    border: 2px solid black;
    margin: 10px;
}
```

### `box-sizing`

`width` batek zer neurtzen duen zehazteko erabiltzen da:

- `box-sizing: content-box;` (lehenetsia): `width`-ek **edukiaren** zabalera bakarrik adierazten du. Padding eta border gehitu egiten dira, eta kutxa idatzitakoa baino handiagoa geratzen da.
- `box-sizing: border-box;`: `width`-ek **kutxa osoaren** zabalera adierazten du (edukia + padding + border). Gaur egun **oso gomendagarria** da, kalkuluak asko errazten dituelako.

```
* {
    box-sizing: border-box;
}
```


!!! tip "Aholkua"
    Proiektu berri baten hasieran, ohikoa da `*  { box-sizing: border-box; }` jartzea CSS fitxategiaren hasieran, kutxen kalkulua errazteko.

## Neurri-unitateak

- **Absolutuak**: `px` (pixela, ohikoena), `cm`, `mm`, `in`, `pt`.
- **Erlatiboak**: pantailaren edo gurasoaren araberakoak dira, eta gaur egun **hauek dira gomendatuenak**, diseinu erantzunkorra (responsive) lortzeko:
    - `%`: gurasoaren neurriaren araberakoa.
    - `em`: elementuaren letra-tamainaren araberakoa.
    - `rem`: **dokumentu osoaren** oinarrizko letra-tamainaren araberakoa (`<html>`-ena). `em` baino erabilgarriagoa da, ez baita metatzen elementu habiaratuetan.
    - `vw` / `vh`: leihoaren zabaleraren / altueraren % (`1vw` = leihoaren zabaleraren %1).

```
html {
    font-size: 16px;
}
h1 {
    font-size: 2rem; /* 32px beti, mailatik edo habiaratzetik independente */
}
.banner {
    height: 50vh; /* pantailaren altueraren erdia */
}
```

## Koloreak

| Modua | Adibidea | Azalpena |
| --- | --- | --- |
| Izena | `color: red;` | Ingelesezko izena. |
| Hamaseitarra | `color: #ff0000;` | Gorria, berdea, urdina (00-FF). |
| Hamaseitar laburtua | `color: #f00;` | Digitu bakarra kolore bakoitzeko. |
| RGB | `color: rgb(255, 0, 0);` | 0-255 arteko balioak. |
| RGBA | `color: rgba(255, 0, 0, 0.5);` | RGB + opakutasuna (0-1). |
| HSL | `color: hsl(0, 100%, 50%);` | Ñabardura, saturazioa, argitasuna. |

!!! tip "Aholkua"
    `rgba()` eta `hsl()` oso erabilgarriak dira gardentasuna behar denean, adibidez atzeko plano erdi-gardenak egiteko.

## Tipografia eta testu-formatua

| Propietatea | Azalpena | Adibidea |
| --- | --- | --- |
| `font-family` | Letra-tipoaren familia. | `font-family: Arial, sans-serif;` |
| `font-size` | Letra-tamaina. | `font-size: 18px;` |
| `font-weight` | Letra-lodiera (100-900, `normal`, `bold`). | `font-weight: bold;` |
| `font-style` | Estiloa. | `font-style: italic;` |
| `line-height` | Lerro-artea. | `line-height: 1.5;` |
| `text-align` | Lerrokadura (`left`, `right`, `center`, `justify`). | `text-align: center;` |
| `text-decoration` | Apaingarria (`underline`, `line-through`, `none`). | `text-decoration: none;` |
| `text-transform` | Maiuskula/minuskula (`uppercase`, `lowercase`, `capitalize`). | `text-transform: uppercase;` |
| `letter-spacing` | Karaktereen arteko tartea. | `letter-spacing: 1px;` |
| `text-shadow` | Testuaren itzala (horizontala, bertikala, kolorea). | `text-shadow: 2px 2px gray;` |

!!! warning "Kontuz"
    `font-family`-rekin: erabiltzaileak ez badu letra-tipo hori instalatuta, nabigatzaileak bere ordezkoa erabiliko du. Horregatik ohikoa da hainbat aukera jartzea lehentasun-hurrenkeran, azkenengoa familia generiko bat izanik:
    ```
    p {
        font-family: "Segoe UI", Arial, sans-serif;
    }
    ```

!!! tip "Google Fonts"
    **Google Fonts** bezalako zerbitzuek doako letra-tipoak eskaintzen dituzte, erraz txertatzeko `<link>` etiketa baten bidez.

## Atzeko planoa (background)

| Propietatea | Azalpena |
| --- | --- |
| `background-color` | Atzeko planoaren kolorea. |
| `background-image` | Atzeko planoko irudia (`url(...)`). |
| `background-repeat` | Errepikapena (`no-repeat`, `repeat-x`, `repeat-y`). |
| `background-position` | Kokapena (`center`, `top left`...). |
| `background-size` | Tamaina (`cover`, `contain`, neurriak). |
| `background-attachment` | Scroll egitean nola jokatzen duen (`fixed`, `scroll`). |

```
body {
    background-image: url("irudiak/atzekoa.jpg");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
}
```

Modu laburrean (shorthand):

```
body {
    background: #ffffff url("irudiak/atzekoa.jpg") no-repeat fixed center;
}
```

## Ertzak (border) eta outline

```
div {
    border-width: 2px;
    border-style: solid;
    border-color: black;
    border-radius: 8px; /* izkinak biribiltzeko */
}
```

Modu laburrean: `border: 2px solid black;`

Ertz banaka alda daitezke: `border-top-color`, `border-bottom-width`, etab.

**`outline`** ertzaren antzekoa da, baina ez da kutxaren neurrien parte, eta ez du espaziorik hartzen. Elementuak nabarmentzeko erabili ohi da (adib. `input:focus`):

```
input:focus {
    outline: 2px solid blue;
}
```

## Margin eta padding

Bien sintaxia berdina da: lau balio, erlojuaren orratzen norabidean (goitik hasita: goian, eskuinean, behean, ezkerrean).

```
div {
    margin: 10px 20px 10px 20px;  /* goian eskuinean behean ezkerrean */
    padding: 10px 20px;           /* goian/behean 10px, ezkerrean/eskuinean 20px */
}
```

Norabide bakarra alda daiteke: `margin-top`, `padding-left`, etab.

!!! tip "Aholkua"
    `margin: 0 auto;` da elementu bat **horizontalki zentratzeko** modurik ohikoena, betiere elementuak `width` zehaztua badu eta `display: block;` bada.

## `display`: elementu motak

- **block**: bere lerro propioa sortzen du (`<div>`, `<p>`, `<h1>`...). Altuera eta zabalera alda dakizkioke.
- **inline**: ez du lerro-jauzirik sortzen (`<span>`, `<a>`, `<b>`...). Altuera/zabalera **ezin dira** aldatu.
- **inline-block**: lerro barruan geratzen da, baina altuera/zabalera aldatu daitezke.
- **none**: elementua ezkutatzen du erabat (ez du lekurik hartzen).

```
span {
    display: inline-block;
    width: 100px;
}
```

## Kokapena: `position`

| Balioa | Azalpena |
| --- | --- |
| `static` | Lehenetsia. Fluxu normalean kokatzen da. |
| `relative` | Bere kokapen normaletik desplazatzen da (`top`, `left`...), baina lekua gordetzen du. |
| `absolute` | `position: relative` (edo antzekoa) duen gurasoarekiko kokatzen da. Ez du lekurik gordetzen. |
| `fixed` | Pantailarekiko finko geratzen da, scroll egin arren. |
| `sticky` | Fluxu normalean doa harik eta zehaztutako mugara iritsi arte; orduantxe `fixed` bihurtzen da. |

```
.menu {
    position: sticky;
    top: 0;
    background-color: white;
}
```

## Float eta clear

Historikoki, orriak maketatzeko `float` asko erabili izan da: elementu bat ezkerrera edo eskuinera "flotarazten" du, eta gainerako testua/elementuak inguruan kokatzen dira.

```
img {
    float: left;
    margin-right: 10px;
}
```

`clear` propietatea flotazio bati "atxikita" ez egoteko erabiltzen da:

```
footer {
    clear: both;
}
```

!!! note
    Gaur egun `float` **ez da gomendagarria** orri osoak maketatzeko; horretarako **Flexbox** eta **Grid** erabiltzen dira (hurrengo puntuetan ikusiko ditugu). `float` erabilera nagusia gaur egun irudi txiki bat testuz inguratzea da.

!!! example "Ariketa 3"
    Kutxen eredua eta kokapena praktikatzeko ariketa hau egingo dugu: *(ariketaren esteka hemen gehituko da)*

## Flexbox

**Flexbox** elementuak lerro batean (edo zutabe batean) modu malguan antolatzeko erabiltzen da. Edukiontzi bati (`display: flex`) ezartzen zaio, eta bere seme guztiak automatikoki antolatzen ditu.

```
.edukiontzia {
    display: flex;
}
```

### Edukiontziaren propietate nagusiak

| Propietatea | Balioak | Azalpena |
| --- | --- | --- |
| `flex-direction` | `row` \| `row-reverse` \| `column` \| `column-reverse` | Elementuak lerroan ala zutabean antolatzen dituen. |
| `flex-wrap` | `nowrap` \| `wrap` | Elementuak lerro/zutabe berrira pasatzen diren edo ez, lekurik ez badago. |
| `justify-content` | `flex-start` \| `flex-end` \| `center` \| `space-between` \| `space-around` | Elementuak nola banatzen diren ardatz nagusian (normalean horizontalean). |
| `align-items` | `flex-start` \| `flex-end` \| `center` \| `stretch` | Elementuak nola lerrokatzen diren ardatz gurutzatuan (normalean bertikalean). |

```
.menu {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
```

### Semeen propietate nagusia

`flex-grow` propietateak elementu batek gainerako espazio librea zenbat "hartu" behar duen adierazten du:

```
.card {
    flex-grow: 1; /* espazio librea era berean banatzen du elementu guztien artean */
}
```

!!! tip "Aholkua"
    Flexbox oso erabilgarria da menu bat, txartel-multzo bat edo elementu-zerrenda bat lerrokatzeko. Kutxen zerrenda bat (1 dimentsiokoa: lerroa edo zutabea) maketatzeko da bereziki egokia.

## Grid

**Grid** sistemarekin edukiontzi bat sareta (errenkadak eta zutabeak) moduan antolatzen da. Flexbox ez bezala, **bi dimentsiotan** (lerroan eta zutabean) lan egiteko pentsatuta dago.

```
.edukiontzia {
    display: grid;
    grid-template-columns: 200px 1fr 1fr;
    grid-template-rows: auto 1fr auto;
    gap: 10px;
}
```

- `grid-template-columns` / `grid-template-rows`: zutabeen/errenkaden neurriak zehazten dituzte. `fr` unitateak "zati bat" adierazten du espazio librearekiko (adib. `1fr 2fr` bigarren zutabea lehenengoa baino bi aldiz zabalagoa izango da).
- `gap`: sareta osatzen duten kutxen arteko tartea.

Elementu bat sareta barruan kokatzeko:

```
.buruko_atala {
    grid-column: 1 / 4; /* 1. zutabetik 4.era */
    grid-row: 1;
}
```

!!! tip "Aholkua"
    Erabaki azkarra: orri baten **egitura orokorra** (buruko atala, alboko barra, edukia, oina) maketatzeko, Grid da normalean aukerarik erosoena. Elementu batzuk lerro batean lerrokatzeko (menu bat, botoi-zerrenda bat), Flexbox nahikoa da.

## Media Queries: diseinu erantzunkorra

*Media queries*-en bidez, pantailaren neurriaren (edo beste ezaugarrien) arabera CSS ezberdina aplika daiteke. Horri **diseinu erantzunkorra** (responsive design) deitzen zaio.

```
/* Pantaila 600px baino handiagoa denean */
@media screen and (min-width: 600px) {
    .edukiontzia {
        display: flex;
    }
}

/* Pantaila 599px edo txikiagoa denean */
@media screen and (max-width: 599px) {
    .edukiontzia {
        display: block;
    }
}
```

Erabilgarrienak diren aldagaiak `min-width` eta `max-width` dira, baina `orientation: portrait` / `orientation: landscape` ere erabil daitezke gailua horizontalki edo bertikalki dagoen egiaztatzeko.

!!! tip "Ez ahaztu"
    Gaur egun HTMLren `<head>` atalean beti jarri behar dugu ondorengo lerroa, media queriek gailu mugikorretan ondo funtziona dezaten:
    ```
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    ```

!!! example "Ariketa 4"
    Flexbox, Grid eta Media Queries praktikatzeko ariketa hau egingo dugu: *(ariketaren esteka hemen gehituko da)*

## Gaur egungo praktika onak: CSS aldagaiak (custom properties)

CSS3k **berezko aldagaiak** onartzen ditu, `--izena` sintaxiarekin. Kolore-paleta edo neurri errepikakorrak kudeatzeko oso erabilgarriak dira, aldaketa bakar batekin CSS osoa eguneratu ahal izateko:

```
:root {
    --kolore_nagusia: #2a7de1;
    --tarte_estandarra: 16px;
}

h1 {
    color: var(--kolore_nagusia);
}

.card {
    padding: var(--tarte_estandarra);
}
```

Gomendioak

✅ Erabili beti kanpoko CSS fitxategiak (ez inline estiloak).

✅ Erabili `box-sizing: border-box;` proiektu guztietan.

✅ Diseinua egiteko, hobetsi **Flexbox** eta **Grid**, `float` baino.

✅ Erabili unitate erlatiboak (`%`, `rem`, `vw/vh`) diseinu erantzunkorra errazteko.

❌ Ez erabili `!important` estiloak "konpontzeko"; ia beti hautatzaileen espezifikotasuna hobeto ulertuz konpon daiteke arazoa.

## Esteka erabilgarriak

- [MDN: CSS](https://developer.mozilla.org/es/docs/Web/CSS)
- [CSS-Tricks: A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [CSS-Tricks: A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Google Fonts](https://fonts.google.com/)