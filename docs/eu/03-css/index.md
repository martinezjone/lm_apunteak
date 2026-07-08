# CSS

CSSk kanpoko estilo-orrien bidez web orriei estiloa emateko aukera ematen
du, horrek fitxategi HTML asko aldatzea ahalbidetzen du CSS dokumentu
bakar bat eguneratuz. Estiloa zuzenean etiketa bakoitzean idaztea **oso
gutxi praktikoa** da; kanpoko estilo-orriak erabiltzea gomendagarria da.

## Oinarrizko sintaxia

```css
selektore {
    propietatea: balioa;
}
```

CSS arau batek hiru zati ditu: **selektorea** (zein elementu eragiten
duen), **propietatea** (zer aldatuko den) eta **balioa** (zenbat edo nola
aldatzen den).

## CSS txertatzeko moduak

1. Lerroan: `<p style="color:red;">`
2. Barnekoa: `<style>` `<head>`-en barruan
3. Kanpokoa: `<link rel="stylesheet" href="estiloak.css">`

## Selektoreak

| Selektorea | Adibidea | Deskribapena |
|---|---|---|
| Elementua | `h1` | `<h1>` guztiak |
| Hainbat elementu | `h1, h2` | `<h1>` eta `<h2>` guztiak |
| Klasea | `.nabarmendua` | `class="nabarmendua"` duten elementuak |
| ID-a | `#menua` | `id="menua"` duen elementua |
| Elementua + klasea | `h1.titulua` | `class="titulua"` duen `<h1>` |
| Elementua + id-a | `h1#egunkoberria` | `id="egunkoberria"` duen `<h1>` |
| Ondorengoa | `ul li` | `<ul>`-ren barruan edozein mailatan dagoen `<li>` |
| Seme zuzena | `ul>li` | `<ul>`-ren seme zuzena den `<li>` |
| Anaia hurbila | `div + p` | `<div>` baten ondoren berehala dagoen `<p>` |

**Klaseak vs. IDak:** **id** batek elementu bakar bat modu bakarrean
identifikatzen du (orriko behin bakarrik erabili beharko litzateke);
**klase** bat estilo bera partekatzen duten hainbat elementutan aplika
daiteke. Selektorean, id-a `#`-rekin erreferentziatzen da eta klasea
`.`-rekin.

## Pseudo-klaseak

Elementuaren egoeraren arabera estiloa aplikatzen dute:

- `a:link` — bisitatu gabeko esteka.
- `a:visited` — bisitatutako esteka.
- `a:active` — esteka klik egiten ari den bitartean.
- `p:hover` — kurtsorea elementuaren gainean dagoen bitartean.
- `input:checked` — hautatutako laukiak edo aukera-botoiak.
- `p:first-of-type` — bere motako lehen elementua.
- `p:first-child` / `p:last-child` — bere gurasoaren lehen/azken semea.
- `p:nth-child(4)` — laugarren semea.
- `p:nth-child(even)` / `p:nth-child(odd)` — seme bikoitiak/bakoitiak.

## Atzeko planoak eta irudiak

- `background-image: url("bidea")` — atzeko planoko irudia.
- `background-repeat: no-repeat | repeat-x | repeat-y` — irudiaren
  mosaikoaren kontrola.
- `background-position: top | bottom | left | right | center` — irudiaren
  posizioa.
- `background-size` — irudiaren dimentsioak kontrolatzen ditu.
- `background-attachment: fixed` — scroll egitean atzeko plano finkoaren
  efektuak sortzen ditu.

## Ertzak

- `border-style: solid | double | dashed | dotted | inset | outset`
- `border-color` — CSSren edozein kolore-notazio onartzen du.
- `border-width` — ertzaren lodiera.
- Posizio araberako aldaerak: `border-bottom-style`, `border-top-color`,
  etab.
- `border-radius: 2px` — izkinak biribiltzen ditu.

## Testu propietateak

- `text-align: left | right | center | justify`
- `font-family` — tipografia adierazten du (Google Fonts-ek txertatutako
  letra-tipoak erabiltzeko aukera ematen du, sisteman instalatuta egon
  behar izan gabe).
- `text-decoration: underline | line-through | none`
- `letter-spacing: 2px` — karaktereen arteko tartea.
- `word-spacing` — hitzen arteko tartea.
- `line-height` — lerroen arteko bereizketa.
- `text-shadow: 2px 3px blue` — testu-itzala (desplazamendu horizontala,
  desplazamendu bertikala, kolorea).
- `text-transform: uppercase | lowercase | capitalize`

## Outline-ak (kanpoko ertzak)

`border`-etik ezberdin, `outline`-ak ez du elementuaren dimentsiorik
eragiten, baina erraz gainjar daiteke beste elementu batzuekin:

- `outline-style: solid | dotted`
- `outline-width: thin | medium | thick`
- `outline-color`
- `outline-offset` — outline eta ertzaren arteko bereizketa.

## Taulak

- `border: solid 1px black` — taulako elementuei ertzak gehitzen dizkie.
- `border-collapse: collapse` — ondoko ertzak fusionatzen ditu.
- `tr:nth-child(even)` — txandakako errenkadak.
- `tr:hover { background-color: red; }` — sagua gainetik pasatzean
  errenkada nabarmentzen du.

## Kutxa eredua (Box Model)

CSSn **dena kutxa bat da**, lau geruzek osatua:

`content` → `padding` → `border` → `margin`

- **Lerroko elementuak** (`<b>`, `<span>`, `<img>`): ez dute lerro-fluxua
  apurtzen eta `width`/`height` aldaketak ez dituzte kontuan hartzen.
- **Bloke-elementuak** (`<div>`, `<p>`, `<ul>`): lerro berria sortzen dute
  eta bai onartzen dituzte tamaina-aldaketak.

`display` propietateak jokabide hori kontrolatzen du:

- `display: block` — bloke bat bezala jokatzen du.
- `display: inline` — lerroan fluitzen du.
- `display: inline-block` — lerroan fluitzen du baina `width`/`height`
  onartzen ditu.

### `box-sizing`

- `box-sizing: content-box` (lehenetsia) — `width`-ak edukira bakarrik
  erreferentzia egiten dio; ertzak batu egiten dira tamaina osoa
  handituz.
- `box-sizing: border-box` — `width`-ak ertzak barne hartzen ditu;
  edukia txikitu egiten da ertzak gehitzean.

## Kokapena

- `position: static` — nabigatzaileak kontrolatutako kokapen lehenetsia.
- `position: relative` — bere posizio naturalarekiko desplazatzen da.
- `position: absolute` — kokatutako aurrekari baten araberakoa da,
  scroll egitean fluxutik "desagertu" daitekeelarik.
- `position: fixed` — pantailan finko mantentzen da scrollari kasurik
  egin gabe.
- `position: sticky` — erdi-finkoa: orriarekin batera mugitzen da
  gutxieneko posizio bat lortu arte (`top`, `left`... erabiliz
  definitua) eta hortik aurrera finko geratzen da.

### Elementuak zentratzea

**Horizontala:**

- Lerroko elementuak: guraso-edukiontziari `text-align: center` aplikatzen
  zaio.
- Bloke-elementuak: `width` bat eta `margin: auto` ematen zaie (edo
  `margin: 40px auto`).
- `inline-block` elementuak: elementuak berak `width` behar du, eta
  gurasoari `text-align: center` aplikatzen zaio.

**Bertikala:**

- Gurasoa `display: table`-rekin eta semeak `display: table-cell` gehi
  `vertical-align: middle`-rekin.
- Alternatiba erraza: `padding` bera goian eta behean.

## Float

`float`-ek inguruko edukiak elementu flotatzailearen ondoan gelditzen den
tokia betetzeko aukera ematen du. Hainbat elementu flotatzaile daudenean
`clear: both` beharrezkoa izan daiteke nahi ez diren gainjartzeak
saihesteko; diseinu konplexuetan sarritan edukiontzi gehigarri bat behar
izaten da flotatzaileak "garbitzeko".

## Marjinak eta padding-a

`padding-` eta `margin-` propietateek (`-top`, `-bottom`, `-left`,
`-right` aldaerekin) barne- eta kanpo-espazioa kontrolatzen dute,
hurrenez hurren.

## Koloreak

- Kolore-izenak: `red`, `yellow`, `green`...
- RGB: `rgb(255, 0, 0)` (0tik 255erako balioak).
- Hamaseitarra: `#ffffff` (gorri, berde eta urdin osagaiak).
- HSL: `hsl(num, num, num)`.

## Neurri-unitateak

- `1cm`, `1in` — inprimatzeko estilo-orrietarako erabilgarriak.
- `1px` — pantailaren bereizmenaren araberakoa.
- `1%` — pantailako maketaziorako egokia.
- `1em` — uneko letra-tipoko "m" letraren zabalera gutxi gorabehera.

## Flexbox

`display: flex`-ek edukiontzi malguak sortzen ditu, bere semeak modu
eraginkorrean banatzen dituztenak.

**Norabidea:**

- `flex-direction: row` — horizontala, ezkerretik eskuinera (lehenetsia).
- `flex-direction: row-reverse` — horizontala, eskuinetik ezkerrera.
- `flex-direction: column` — bertikala, goitik behera.
- `flex-direction: column-reverse` — bertikala, behetik gora.

**Lerro-egokitzea:**

- `flex-wrap: nowrap` — elementuak errenkada bakarrean estutzen dira
  (lehenetsia).
- `flex-wrap: wrap` — soberan geratzen diren elementuak hurrengo
  errenkadara pasatzen dira.
- `flex-wrap: wrap-reverse` — soberan geratzen diren elementuak aurreko
  errenkadara pasatzen dira.

Forma laburtua erabil daiteke: `flex-flow: column wrap`.

**Banaketa horizontala (`justify-content`):**

- `flex-start` — ezkerrera lerrokatuta, espazioa eskuinean.
- `flex-end` — eskuinera lerrokatuta, espazioa ezkerrean.
- `space-between` — muturretako elementuek ertzak ukitzen dituzte;
  espazioa gainerakoen artean banatzen da.
- `space-around` — espazioa modu ez-uniformean banatzen da, marjina
  txikiagoekin muturretan.
- `space-evenly` — espazioa erabat uniformeki banatzen da.

## Grid Layout

`display: grid`-ek taula moduko egiturak sortzen ditu, gelaxken kokapen
malguarekin.

```css
.edukiontzia {
    display: grid;
    grid-template-rows: 20% 20% 20% 20% 20%;
    grid-template-columns: 20% 20% 20% 20% 20%;
}
.elementua {
    grid-row: 1/3;
    grid-column: 4/6;
}
```

- `grid-template-rows` / `grid-template-columns`-ek errenkaden eta
  zutabeen proportzioak definitzen dituzte.
- `grid-row: 1/3` — 1. errenkadatik 3.era arte hartzen du (1 eta 2.
  errenkadak).
- `grid-column: 4/6` — 4. zutabetik 6.era arte hartzen du (4 eta 5.
  zutabeak).

## Media Queries

Irteera-euskarriaren arabera CSS baldintzatua aplikatzeko aukera ematen
dute:

```css
@media screen {
    div { font-size: xx-large; }
}
@media print {
    div { margin: 15px; }
}
```

**Puntu erresponsiboak:**

- `@media screen and (min-width: 800px)` — 800px edo gehiagoko pantailak.
- `@media screen and (max-width: 799px)` — 800px baino estuagoko
  pantailak.
- `@media (orientation: portrait)` — orientazio bertikala.
- `@media (orientation: landscape)` — orientazio horizontala.

## Tipografia

`font-family: "Arial"`-ek komaz bereizitako hainbat lehentasun adierazteko
aukera ematen du, lehena erabilgarri ez badago alternatiba gisa. Hainbat
letra-tipo familia daude: **serif** (errematedun apainduak),
**sans-serif** (lerro garbiak, apaindurarik gabe) eta **espazio
bakarrekoak** (karaktere guztiek zabalera bera dute).

## Formularioei estiloa ematen

Ohiko planteamenduak:

- `display: block` label/input-etan kontrolak bertikalki pilatzeko.
- `margin-bottom: 50px` elementuak bereizteko.
- `width: 80%` eremuei zabalera uniformea emateko.
- `padding: 10px` barne-espaziorako.
- `input:focus` eremua aktibo dagoenean estiloa aplikatzeko.
- `padding` `fieldset`-ean barne-marjina bat sortzeko.

## Bootstrap

Gutxieneko egitura HTML bat behar duen CSS framework-a,
`<div class="container">` bat inguruan duena. 12 zutabeko sare-sistema
(*grid*) erresponsiboa erabiltzen du.

**Zutabe-klaseak gailuaren zabaleraren arabera:**

- `col-xs-3` — oso txikia (< 768px).
- `col-sm-3` — txikia (768–992px).
- `col-md-6` — ertaina (~992px).
- `col-lg-9` — handia (> 992px).

**Beste utilitate batzuk:**

- `class="lead"` — paragrafo bat nabarmentzen du.
- `<mark>` — testua horiz nabarmentzen du.

## LESS (aurreprozesatzailea)

CSS programazio-ezaugarriekin zabaltzen du eta CSS estandarra sortzen du
irteera gisa.

**Aldagaiak** (`@` aurrizkia, eragiketa matematikoak onartzen dituzte):

```less
@ertzlodiera: 3px;
@goiburulodiera: @ertzlodiera + 2px;
border: solid @ertzlodiera black;
```

**Mixin-ak** (funtzio gisa deitzen diren definizio berrerabilgarriak,
kodea errepikatzea saihestuz):

```less
.berrienmarjinak {
    padding-top: 10px;
    margin: 20px 10px 20px 10px;
}
#kutxa1 { .berrienmarjinak(); }
```
