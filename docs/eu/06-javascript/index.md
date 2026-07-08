# JavaScript

## Sarrera

JavaScript Netscape-n sortu zen eta **ez du zerikusirik Javarekin**,
izenaz gain. Ezaugarri gakoak:

- Nabigatzaileak **interpretatzen** du, ez da bytecode-ra konpilatzen.
- **ECMAScript** gisa estandarizatuta dago, nahiz eta betetze-maila
  nabigatzailearen arabera aldatu.
- **Prototipoetan** oinarritua dago, ez klaseetan (nahiz eta ES6-k eredu
  horren gainean klase-sintaxi bat gehitzen duen).
- **Tipaketa ahula** du: motaren bihurketa automatikoak baimentzen ditu.

## Datu-motak

JavaScriptek hauek onartzen ditu: zenbakiak, testu-kateak, boolearrak
(balio logikoak), `undefined` (hasieratu gabeko aldagai bati sartzean) eta
`null` (balio-eza nahitakoa adierazten du).

`"use strict"` direktibak lengoaiaren arau zorrotzagoak betetzera behartzen
du, adibidez deklaratu gabeko aldagaietara sartzea eragotziz.

## Konstanteak eta aldagaiak

Aldagaiak `let`-ekin deklaratzen dira (gaur egungo estandarra) edo
zaharkituta dagoen `var`-ekin; balio aldaezinak `const`-ekin deklaratzen
dira:

```javascript
"use strict"
const grabitatea = 9.81;
let posizioa = 42;
```

## Kateen kontkatenazioa

Kontkatenazio tradizionalak `+` eragilea erabiltzen du:

```javascript
let izenOsoa = izena + " " + abizena1 + " " + abizena2;
```

ES6ren *template literals*-ek (alderantzizko komatxoak) sintaxi
garbiagoa eskaintzen dute:

```javascript
let izenOsoa = `${izena} ${abizena1} ${abizena2}`;
```

## HTMLn txertatzea

```html
<script src="script.js" defer></script>
```

Kodea zuzenean `<script>` eta `</script>` artean ere sar daiteke, bai
`<head>`-en bai `<body>`-n:

```javascript
"use strict"
let nireAldagaia = 42;
document.write(nireAldagaia);
```

## Kontrol-egiturak

`if-else`-k Javan bezala funtzionatzen du, eragile logiko berdinekin
(`&&`, `||`):

```javascript
if (aldagaiA > aldagaiB) {
    document.write("Lehena handiagoa da");
} else {
    document.write("Bigarrena handiagoa da");
}
```

## Arrayak

Arrayek mota ezberdinetako elementuak onartzen dituzte eta dinamikoki
tamaina aldatzen dute:

```javascript
let izenak = new Array();
izenak[0] = "Juan Perez";
izenak[1] = "Pedro Diaz";

let zenbakiak = new Array(2);
zenbakiak[0] = 23;
zenbakiak[1] = -45.23;
```

## `for` bukla

For klasikoa, array-aren luzera `.length`-rekin atzituz:

```javascript
for (let i = 0; i < zenbakiak.length; i++) {
    document.write("Posizioa " + i + ": " + zenbakiak[i]);
}
```

*Foreach* estiloko iterazioa `for...in`-ekin:

```javascript
for (let posizioa in zenbakiak) {
    document.write("Posizioa " + posizioa + ": " + zenbakiak[posizioa]);
}
```

## `while` bukla

```javascript
let pos = 0;
while (pos < zenbakiak.length) {
    document.write(zenbakiak[pos]);
    pos++;
}
```

## Funtzioak

Funtzioek parametroak onartzen dituzte eta `return`-ekin balio bat
itzultzen dute:

```javascript
function batazbestekoaKalkulatu(balioak) {
    let batura = 0;
    for (let pos in balioak) {
        batura = batura + balioak[pos];
    }
    return batura / balioak.length;
}
```

Funtzioak esleitu daitezkeen balioak dira: esleitzean parentesiak kentzen
dira, eta exekutatzean sartzen dira:

```javascript
let agurra = agurEgin; // esleipena
agurra("Tom");          // exekuzioa
```

ES6-k balio lehenetsidun parametroak baimentzen ditu:

```javascript
function agurtu(agurra = "Kaixo", pertsona = "Jon") {
    alert(`${agurra} ${pertsona}`);
}
```

## Objektuei zuzendutako programazioa

JavaScriptek klase bat definitu beharrik gabe objektuak sortzeko aukera
ematen du:

```javascript
let langilea = {
    izena: "Pepe Perez",
    adina: 27,
    erretiratutaDago: function() {
        return this.adina > 65;
    }
};
document.write(langilea.izena);
document.write(langilea.erretiratutaDago());
```

## DOM manipulazioa

```js
const titulua = document.querySelector("h1");
titulua.textContent = "Titulu berria";
```

## Ekitaldiak (events)

```js
document.querySelector("button").addEventListener("click", () => {
    alert("Kaixo!");
});
```

## jQuery

jQueryk `$` funtzioa erabiltzen du CSS selektoreen bidez elementuak
hautatzeko, bere metodo eta propietate propioak dituen objektu bat
itzuliz.

### Ekitaldien kudeaketa

`click` metodoak funtzio bat sakatze-ekitaldi bati lotzen dio:

```javascript
$(document).ready(hasieratu);

function hasieratu() {
    let botoia = $("#id-botoia");
    botoia.click(klikaKudeatu);
}

function klikaKudeatu() {
    let div = $("#testu-dib");
    div.fadeOut();
}
```

!!! warning "Garrantzitsua"
    Funtzioak erreferentziaz pasatzen dira (parentesirik gabe)
    `.ready()`-ri eta `.click()`-i. Parentesiak gehituz gero, funtzioa
    berehala exekutatzen da, ekitaldiari lotu ordez.

Ohiko beste ekitaldi batzuk: `click`, `dblclick`, `mouseover`.

### Atributuen irakurketa eta idazketa

Eremu baten balioa irakurtzeko `.val()` erabiltzen da, eta checkbox edo
radio bat markatuta dagoen egiaztatzeko, `.prop("checked")`:

```javascript
function generoaKudeatu() {
    let testuKoadroa = $("#txostena");
    testuKoadroa.val("Ongi etorri Jn.");
}

let checkboxa = $("#autobusa");
checkboxa.click(hautatutakoakZenbatu);

function hautatutakoakZenbatu() {
    let guztira = 0;
    let idak = ["#autobusa", "#autoa", "#bizikleta", "#trena"];
    for (let pos in idak) {
        if ($(idak[pos]).prop("checked")) {
            guztira++;
        }
    }
}
```

Zerrenda desplegagarrien balioak ere `.val()`-ekin irakurtzen dira.

### Beste metodo erabilgarri batzuk

- `.slideDown()` / `.slideUp()` — irristatze-animazioarekin erakusten/
  ezkutatzen dute.
- `.fadeOut()` / `.fadeIn()` — iraungitze-efektuak.
- `.addClass()` / `.removeClass()` — CSS klaseak dinamikoki gehitzen/
  kentzen dituzte.
- `.html()` — elementu baten barne-edukia aldatzen du.

### Negozio-arauen balidazioa

Ohiko patroi bat aukera bateraezinen konbinazioak balidatzea da,
adibidez "diesel motor batek ezin du 2300cc gainditu":

```javascript
function konfigurazioaBaliozkoaDa() {
    if ($("#diesela").prop("checked") && $("#2300cc").prop("checked")) {
        alert("Bateraezina: diesela 2300cc-rekin");
        return false;
    }
    return true;
}
```

Horrelako egiaztapenek aplikazio interaktiboak eraikitzeko aukera ematen
dute: balidaziodun formularioak, prezio-kalkulagailuak, produktu-
konfiguratzaileak, etab., interfazea erabiltzailearen hautaketen arabera
eguneratuz.

## Datuen fetch-a

```js
fetch("datuak.json")
    .then(response => response.json())
    .then(datuak => console.log(datuak));
```
