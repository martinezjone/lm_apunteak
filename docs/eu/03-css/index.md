# CSS

CSS (**Cascading Style Sheets**) web-orri baten **itxura eta diseinua**
definitzeko erabiltzen den lengoaia da.

HTML dokumentuaren egitura eta edukia definitzeko erabiltzen dugu; CSS
bidez, berriz, elementu horien itxura alda dezakegu.

Adibidez, HTML dokumentu honetan:

``` html
<h1>Nire lehen web-orria</h1>
<p>Hau paragrafo bat da.</p>
```

CSS erabiliz, izenburuaren kolorea eta paragrafoaren tamaina alda
ditzakegu:

``` css
h1 {
    color: blue;
}

p {
    font-size: 18px;
}
```

!!! tip "HTML eta CSS"

    **HTML → egitura eta edukia**

    **CSS → itxura eta diseinua**

## CSS sintaxia

CSS arau batek **hautatzaile** bat eta deklarazio bat edo gehiago ditu:

``` css
p {
    color: blue;
    font-size: 18px;
}
```

-   `p` → **hautatzailea**: estiloa zein elementuri aplikatuko zaion
    adierazten du.
-   `color`, `font-size` → **propietateak**: zer aldatu nahi dugun
    adierazten dute.
-   `blue`, `18px` → **balioak**: propietateak zer balio izango duen
    adierazten dute.

Deklarazio bakoitzak egitura hau du:

``` css
propietatea: balioa;
```

Deklarazioak `{ }` giltzen artean idazten dira:

``` css
hautatzailea {
    propietatea: balioa;
    propietatea: balioa;
}
```

!!! note "Kontuan izan"

    Propietatea eta balioa `:` bidez bereizten dira, eta deklarazio bakoitzaren amaieran `;` erabiltzen da.

## CSS HTML dokumentuan erabiltzea

CSS HTML dokumentu bati hiru modutan gehi diezaiokegu.

### Inline estiloak

CSS zuzenean HTML elementuaren `style` atributuan idazten da:

``` html
<p style="color: blue;">Paragrafo urdina</p>
```

Metodo hau erabil daitekeen arren, **ez da gomendagarria web-orri baten
estilo orokorra definitzeko**, HTML egitura eta CSS estiloak nahasten
baitira.

### Barneko estilo-orria

CSS kodea dokumentuaren `<head>` barruko `<style>` elementuan idatz
daiteke:

``` html
<head>
    <style>
        p {
            color: blue;
        }
    </style>
</head>
```

Metodo hau erabilgarria izan daiteke orri bakar batean estilo gutxi
batzuk definitzeko.

### Kanpoko estilo-orria

Ohikoena eta gomendagarriena CSS kodea aparteko `.css` fitxategi batean
gordetzea da.

Adibidez, proiektuak honako egitura izan dezake:

``` text
proiektua/
│
├── index.html
└── css/
    └── estiloak.css
```

`estiloak.css` fitxategian:

``` css
h1 {
    color: blue;
}

p {
    font-size: 18px;
}
```

HTML dokumentutik CSS fitxategia lotzeko `<link>` elementua erabiltzen
da, `<head>` barruan:

``` html
<head>
    <link rel="stylesheet" href="css/estiloak.css">
</head>
```

!!! tip "Gomendioa"

    Ahal den guztietan, **kanpoko estilo-orriak** erabiliko ditugu. Horrela HTML egitura eta CSS estiloak bananduta mantentzen dira, eta kodea txukunagoa eta mantentzeko errazagoa da.

### Lehenengo adibidea

Sortu honako egitura:

``` text
lehen-css/
│
├── index.html
└── css/
    └── estiloak.css
```

`index.html`:

``` html
<!DOCTYPE html>
<html lang="eu">
<head>
    <meta charset="UTF-8">
    <title>Nire lehen CSS</title>
    <link rel="stylesheet" href="css/estiloak.css">
</head>
<body>

    <h1>Nire lehen CSS</h1>

    <p>HTML erabiliz web-orriaren egitura sortzen dugu.</p>

    <p>CSS erabiliz web-orriaren itxura aldatzen dugu.</p>

</body>
</html>
```

`estiloak.css`:

``` css
h1 {
    color: darkblue;
}

p {
    color: #333;
    font-size: 18px;
}
```

Aldatu CSS fitxategiko balioak eta ikusi zer gertatzen den
nabigatzailean.

!!! example "Probatu"

    Aldatu `h1` elementuaren `color` propietatea.

    Gehitu `font-size: 40px;`.

    Zer gertatzen da nabigatzailean?

## Hautatzaileak

CSS erabiltzean, lehenengo erabaki behar dugu **zein HTML elementuri
aplikatu nahi diogun estiloa**.

Horretarako **hautatzaileak** erabiltzen ditugu.

### Elementu-hautatzailea

HTML elementu mota bereko elementu guztiak hautatzen ditu.

``` css
p {
    color: blue;
}
```

``` html
<p>Lehenengo paragrafoa</p>
<p>Bigarren paragrafoa</p>
```

Bi paragrafoek estilo bera jasoko dute.

### Hainbat elementu hautatzea

Hainbat elementuri estilo bera aplikatzeko, hautatzaileak komaz
bereizten dira:

``` css
h1, h2, p {
    color: blue;
}
```

Kasu honetan `<h1>`, `<h2>` eta `<p>` elementuek kolore bera izango
dute.

### Class hautatzailea

`class` atributuak hainbat elementu taldekatzea ahalbidetzen du.

HTML:

``` html
<p class="nabarmendua">Paragrafo garrantzitsua</p>
<p>Paragrafo arrunta</p>
<p class="nabarmendua">Beste paragrafo garrantzitsu bat</p>
```

CSS:

``` css
.nabarmendua {
    background-color: yellow;
}
```

CSSn `class` bat hautatzeko **puntua (`.`)** erabiltzen da:

``` css
.klasearen-izena {
    propietatea: balioa;
}
```

`class` bera hainbat HTML elementutan erabil daiteke.

### Elementu batek hainbat class izan ditzake

HTML elementu batek `class` bat baino gehiago izan ditzake. Izenak
zuriunez bereizten dira:

``` html
<p class="nabarmendua handia">Testu garrantzitsua</p>
```

``` css
.nabarmendua {
    background-color: yellow;
}

.handia {
    font-size: 24px;
}
```

Elementuak bi klaseen estiloak jasoko ditu.

### ID hautatzailea

`id` atributua dokumentuko elementu **bakar bat identifikatzeko**
erabiltzen da.

HTML:

``` html
<h1 id="izenburua">Nire web-orria</h1>
```

CSS:

``` css
#izenburua {
    color: darkblue;
}
```

CSSn `id` bat hautatzeko `#` erabiltzen da:

``` css
#id-izena {
    propietatea: balioa;
}
```

!!! note "`class` edo `id`?"

    `class` → hainbat elementutan erabil daiteke.

    `id` → dokumentuko elementu bakarra identifikatzeko erabiltzen da.

    Estiloak aplikatzeko, normalean **class erabiltzea komeni da**.

### Ondorengo elementuak hautatzea

Beste elementu baten barruan dauden elementuak hauta ditzakegu:

``` html
<header>
    <p>Header barruko paragrafoa</p>
</header>

<main>
    <p>Main barruko paragrafoa</p>
</main>
```

``` css
header p {
    color: blue;
}
```

Kasu honetan, `<header>` elementuaren barruan dauden `<p>` elementuek
bakarrik jasoko dute estiloa.

### Hautatzaile unibertsala

`*` hautatzaileak dokumentuko elementu guztiak hautatzen ditu:

``` css
* {
    box-sizing: border-box;
}
```

### Pseudo-klaseak

Pseudo-klaseek elementu baten **egoeraren arabera** estiloa aplikatzeko
aukera ematen dute.

Adibidez, `:hover` pseudo-klasea sagua elementuaren gainean dagoenean
aktibatzen da:

``` css
a:hover {
    color: red;
}
```

Esteketan ohikoak dira:

``` css
a:link {
    color: blue;
}

a:visited {
    color: purple;
}

a:hover {
    color: red;
}

a:active {
    color: orange;
}
```

!!! example "Probatu"

    Sortu hainbat esteka dituen HTML dokumentu bat eta definitu egoera bakoitzerako kolore desberdin bat.

## Cascada, herentzia eta espezifikotasuna

Batzuetan, elementu bati CSS arau batek baino gehiagok eragiten diote.

Adibidez:

``` css
p {
    color: blue;
}

.nabarmendua {
    color: red;
}
```

``` html
<p class="nabarmendua">Zein kolore izango dut?</p>
```

Kasu honetan testua **gorria** izango da, `.nabarmendua` hautatzailea
`p` hautatzailea baino espezifikoagoa delako.

CSSk hainbat arau erabiltzen ditu zein estilo aplikatu erabakitzeko:

-   **Espezifikotasuna**: hautatzaile zehatzagoek lehentasun handiagoa
    dute.
-   **Ordena**: espezifikotasun bera badute, geroago idatzitako arauak
    lehentasuna izango du.
-   **Herentzia**: propietate batzuk guraso-elementutik
    seme-elementuetara heredatzen dira.

Adibidez:

``` html
<section>
    <h2>Izenburua</h2>
    <p>Paragrafoa</p>
</section>
```

``` css
section {
    color: blue;
}
```

`color` heredatzen den propietatea denez, `<h2>` eta `<p>` elementuek
ere kolore urdina hartuko dute.

!!! tip "Ideia nagusia"

    Ez dugu espezifikotasunaren kalkulua buruz ikasi behar. Garrantzitsuena da ulertzea **elementu batek hainbat CSS arau jaso ditzakeela** eta nabigatzaileak erabakitzen duela zein aplikatu.

## Koloreak

CSSn koloreak hainbat modutan adieraz daitezke.

### Kolorearen izena

``` css
p {
    color: red;
}
```

### Notazio hamaseitarra

``` css
p {
    color: #ff0000;
}
```

Notazio laburtua ere erabil daiteke zenbakiak errepikatzen direnean:

``` css
p {
    color: #f00;
}
```

### RGB

RGB sistemak gorriaren (**Red**), berdearen (**Green**) eta urdinaren
(**Blue**) kantitatea adierazten du.

Balio bakoitza `0` eta `255` artekoa da:

``` css
p {
    color: rgb(255, 0, 0);
}
```

Gardentasuna ere zehaztu daiteke:

``` css
p {
    color: rgb(255 0 0 / 50%);
}
```

### HSL

HSL sistemak hiru balio erabiltzen ditu: tonua (**Hue**), saturazioa
(**Saturation**) eta argitasuna (**Lightness**).

``` css
p {
    color: hsl(0, 100%, 50%);
}
```

!!! tip "Gomendioa"

    Ez da beharrezkoa kolore-kodeak buruz ikastea. Garapen-tresnek eta editoreek kolorea aukeratzen laguntzen dute.

## Neurri-unitateak

CSSn propietate askok neurri bat behar dute:

``` css
p {
    font-size: 18px;
}
```

Unitateak **absolutuak** edo **erlatiboak** izan daitezke.

### Unitate absolutuak

Ohikoena `px` da:

``` css
p {
    font-size: 18px;
}
```

Beste unitate absolutu batzuk `cm`, `mm`, `in`, `pt` eta `pc` dira,
baina web-diseinuan gutxiago erabiltzen dira.

### Unitate erlatiboak

Diseinu moldagarriak egiteko oso erabilgarriak dira.

  Unitatea   Erreferentzia
  ---------- ----------------------------------------------------
  `%`        Beste neurri batekiko portzentajea.
  `em`       Elementuaren letra-tamainarekiko.
  `rem`      Dokumentuaren erroko (`html`) letra-tamainarekiko.
  `vw`       Nabigatzailearen zabalerarekiko.
  `vh`       Nabigatzailearen altuerarekiko.

Adibidez:

``` css
main {
    width: 80%;
}

h1 {
    font-size: 2rem;
}

header {
    min-height: 50vh;
}
```

!!! note

    Web-diseinuan ez dugu unitate bakarra erabiliko egoera guztietarako. Aukera egokia aldatu egiten da neurtzen ari garen elementuaren arabera.

## Testua eta tipografia

### Testuaren kolorea

`color` propietateak testuaren kolorea definitzen du:

``` css
p {
    color: #333;
}
```

### Letra-tamaina

``` css
p {
    font-size: 18px;
}
```

### Letra-familia

`font-family` propietateak letra-tipoa definitzen du:

``` css
body {
    font-family: Arial, Helvetica, sans-serif;
}
```

Hainbat letra-tipo jartzea gomendatzen da. Lehenengoa erabilgarri ez
badago, nabigatzaileak hurrengoa probatuko du.

Izenak zuriuneak baditu, komatxo artean idazten dira:

``` css
body {
    font-family: "Times New Roman", serif;
}
```

### Letra-lodiera

``` css
p {
    font-weight: bold;
}
```

Zenbakiz ere adieraz daiteke:

``` css
h1 {
    font-weight: 700;
}
```

### Letra-estiloa

``` css
p {
    font-style: italic;
}
```

### Lerrokatzea

``` css
p {
    text-align: center;
}
```

Ohiko balioak:

-   `left`
-   `right`
-   `center`
-   `justify`

### Lerroartea

`line-height` propietateak testu-lerroen arteko distantzia kontrolatzen
du:

``` css
p {
    line-height: 1.5;
}
```

### Testuaren dekorazioa

``` css
a {
    text-decoration: none;
}
```

Beste balio batzuk:

``` css
.azpimarratua {
    text-decoration: underline;
}

.marratua {
    text-decoration: line-through;
}
```

### Maiuskulak eta minuskulak

``` css
h1 {
    text-transform: uppercase;
}
```

Balio erabilienak:

-   `uppercase`
-   `lowercase`
-   `capitalize`
-   `none`

## Box Model

HTML elementu guztiak **kutxa baten moduan** irudika ditzakegu.

Kutxa bakoitzak lau atal nagusi ditu:

1.  **Content** → elementuaren edukia.
2.  **Padding** → edukiaren eta ertzaren arteko barneko espazioa.
3.  **Border** → elementuaren ertza.
4.  **Margin** → elementuaren kanpoko espazioa.

``` text
+-------------------------+
|         MARGIN          |
|  +-------------------+  |
|  |      BORDER       |  |
|  |  +-------------+  |  |
|  |  |   PADDING   |  |  |
|  |  |  +-------+  |  |  |
|  |  |  |CONTENT|  |  |  |
|  |  |  +-------+  |  |  |
|  |  +-------------+  |  |
|  +-------------------+  |
+-------------------------+
```

### Width eta height

``` css
div {
    width: 300px;
    height: 150px;
}
```

`width` elementuaren zabalera da eta `height` altuera.

### Padding

Elementuaren edukiaren eta ertzaren arteko espazioa da:

``` css
div {
    padding: 20px;
}
```

Alde bakoitza banaka ere defini daiteke:

``` css
div {
    padding-top: 10px;
    padding-right: 20px;
    padding-bottom: 10px;
    padding-left: 20px;
}
```

Forma laburtua:

``` css
div {
    padding: 10px 20px;
}
```

### Border

Elementu baten ertza definitzeko:

``` css
div {
    border-width: 2px;
    border-style: solid;
    border-color: black;
}
```

Normalean forma laburtua erabiltzen da:

``` css
div {
    border: 2px solid black;
}
```

Ertzak biribiltzeko:

``` css
div {
    border-radius: 10px;
}
```

### Margin

Elementuaren kanpoko espazioa definitzen du:

``` css
div {
    margin: 20px;
}
```

Alde bakoitza banaka ere defini daiteke:

``` css
div {
    margin-top: 10px;
    margin-right: 20px;
    margin-bottom: 10px;
    margin-left: 20px;
}
```

Elementu bat horizontalki zentratzeko ohiko aukera:

``` css
main {
    width: 80%;
    margin: 0 auto;
}
```

### `box-sizing`

Lehenespenez, `width` propietateak edukiaren zabalera bakarrik hartzen
du kontuan. `padding` eta `border` gehitu egiten zaizkio.

Horregatik, oso ohikoa da honako araua erabiltzea:

``` css
* {
    box-sizing: border-box;
}
```

`border-box` erabilita, zehaztutako zabalera barruan sartzen dira
`content`, `padding` eta `border`.

!!! tip "Gomendioa"

    Proiektuaren hasieran honako hau erabiltzea ohitura ona da:

    ```css
    * {
        box-sizing: border-box;
    }
    ```

## Atzeko planoa

### Atzeko planoaren kolorea

``` css
body {
    background-color: #f5f5f5;
}
```

### Atzeko planoko irudia

``` css
header {
    background-image: url("../images/fondoa.jpg");
}
```

CSS fitxategian erabiltzen diren bide erlatiboak **CSS fitxategia dagoen
kokalekutik** kalkulatzen dira.

Adibidez:

``` text
proiektua/
│
├── index.html
├── css/
│   └── estiloak.css
└── images/
    └── fondoa.jpg
```

`estiloak.css` fitxategitik `images` karpetara joateko:

``` css
header {
    background-image: url("../images/fondoa.jpg");
}
```

Atzeko planoko irudiekin beste propietate batzuk ere erabil daitezke:

``` css
header {
    background-image: url("../images/fondoa.jpg");
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
}
```

## `display` propietatea

`display` propietateak elementu bat dokumentuan nola antolatzen den
definitzen du.

### Block elementuak

`block` elementuek erabilgarri dagoen zabalera hartzen dute eta hurrengo
elementua beste lerro batean hasten da.

``` css
div {
    display: block;
}
```

HTMLko `<div>`, `<p>`, `<section>` edo `<h1>` bezalako elementuak
`block` dira lehenespenez.

### Inline elementuak

`inline` elementuak edukiarentzako behar duten espazioa bakarrik hartzen
dute eta ez dute lerro-jauzirik sortzen.

``` css
span {
    display: inline;
}
```

`<span>` edo `<a>` bezalako elementuak `inline` dira lehenespenez.

### Inline-block

`inline-block` elementuak lerro berean koka daitezke, baina `width`,
`height`, `padding` eta `margin` propietateak kontrolatzeko aukera
ematen dute.

``` css
a {
    display: inline-block;
    padding: 10px;
}
```

### Elementu bat ezkutatzea

``` css
.elementua {
    display: none;
}
```

Elementua ez da bistaratuko eta ez du espaziorik hartuko.

## Flexbox

Flexbox elementuak **lerro edo zutabe batean antolatzeko** erabiltzen
den CSS sistema da.

Flexbox erabiltzeko, elementuen gurasoari hau aplikatzen zaio:

``` css
.edukiontzia {
    display: flex;
}
```

HTML:

``` html
<div class="edukiontzia">
    <div>1</div>
    <div>2</div>
    <div>3</div>
</div>
```

### Norabidea

``` css
.edukiontzia {
    display: flex;
    flex-direction: row;
}
```

Balio nagusiak:

-   `row`
-   `row-reverse`
-   `column`
-   `column-reverse`

### Ardatz nagusiko lerrokatzea

`justify-content` propietateak elementuak ardatz nagusian banatzen ditu:

``` css
.edukiontzia {
    display: flex;
    justify-content: center;
}
```

Balio erabilienak:

-   `flex-start`
-   `flex-end`
-   `center`
-   `space-between`
-   `space-around`
-   `space-evenly`

### Zeharkako ardatzeko lerrokatzea

``` css
.edukiontzia {
    display: flex;
    align-items: center;
}
```

Balio erabilienak:

-   `stretch`
-   `flex-start`
-   `flex-end`
-   `center`

### Elementuak hurrengo lerrora pasatzea

``` css
.edukiontzia {
    display: flex;
    flex-wrap: wrap;
}
```

### Elementuen arteko tartea

``` css
.edukiontzia {
    display: flex;
    gap: 20px;
}
```

!!! example "Probatu"

    Sortu hiru kutxa dituen edukiontzi bat eta probatu `flex-direction`, `justify-content`, `align-items` eta `gap` propietateen balio desberdinak.

## Grid

CSS Grid elementuak **errenkada eta zutabeetan** antolatzeko erabiltzen
da.

``` css
.edukiontzia {
    display: grid;
}
```

Adibidez, hiru zutabe berdin sortzeko:

``` css
.edukiontzia {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
}
```

Forma laburragoan:

``` css
.edukiontzia {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}
```

Elementuen arteko tartea:

``` css
.edukiontzia {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

!!! note "`fr` unitatea"

    `fr` Grid-en erabiltzen den unitatea da eta erabilgarri dagoen espazioaren zati bat adierazten du.

    `1fr 1fr 1fr` erabiliz, espazioa hiru zati berdinetan banatzen da.

## Diseinu moldagarria

Web-orriak pantaila-tamaina desberdinetara egokitu behar dira:
ordenagailuak, tabletak eta mugikorrak.

Horretarako, besteak beste, neurri erlatiboak, Flexbox, Grid eta **media
queries** erabil ditzakegu.

### Media queries

Media query batek CSS arauak baldintza baten arabera aplikatzeko aukera
ematen du.

Adibidez:

``` css
.edukiontzia {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 768px) {
    .edukiontzia {
        grid-template-columns: 1fr;
    }
}
```

Pantailaren zabalera `768px` edo txikiagoa denean, hiru zutabe izan
beharrean zutabe bakarra izango dugu.

!!! tip "Ideia nagusia"

    Diseinu moldagarria ez da webgunearen amaieran gehitzen den zerbait. Web-orria sortzen dugun momentutik kontuan hartu behar dugu pantaila-tamaina desberdinetan erabiliko dela.

## `float` eta `clear`

`float` propietateak elementu bat ezkerrera edo eskuinera eramateko
aukera ematen du, eta ondorengo edukia haren inguruan kokatzen da.

Adibidez, irudi baten inguruan testua jartzeko:

``` css
img {
    float: left;
    margin-right: 15px;
}
```

Balio nagusiak:

-   `none`
-   `left`
-   `right`

`clear` propietateak aurreko `float` baten eragina kontrolatzeko
erabiltzen da:

``` css
footer {
    clear: both;
}
```

!!! warning "`float` maketaziorako?"

    Garai batean `float` web-orriak maketatzeko asko erabiltzen zen.

    Gaur egun, elementuen kokapena eta web-orriaren maketazioa egiteko **Flexbox eta Grid erabiltzea gomendatzen da**.

    `float` erabilgarria da oraindik, adibidez, **irudi baten inguruan testua kokatzeko**.

## Esteka erabilgarriak

-   [MDN: CSS](https://developer.mozilla.org/en-US/docs/Web/CSS){:
    target="\_blank" rel="noopener" }
-   [MDN: CSS
    selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors){:
    target="\_blank" rel="noopener" }
-   [MDN: CSS Box
    Model](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Box_model){:
    target="\_blank" rel="noopener" }
-   [MDN:
    Flexbox](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Flexbox){:
    target="\_blank" rel="noopener" }
-   [MDN:
    Grid](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Grids){:
    target="\_blank" rel="noopener" }
