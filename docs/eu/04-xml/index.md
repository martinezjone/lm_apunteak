# XML

## Zer da XML?

**XML** (*eXtensible Markup Language*) marka-lengoaia bat da, datuak modu
egituratuan gordetzeko eta garraiatzeko diseinatua, bai pertsonek bai
makinek irakurtzeko modukoa.

HTMLtik ezberdin, honek helburu finkoa eta etiketa-multzo itxia baitu,
XMLk **norberaren marka lengoaiak** (hiztegiak) sortzeko aukera ematen du,
erabiltzaileak berak definituak, programen arteko datu-trukerako
pentsatuak.

## Eraikuntza-arauak

- **Maiuskulak eta minuskulak bereizten ditu**: `<bezeroa>`, `<Bezeroa>`
  eta `<BEZEROA>` hiru etiketa ezberdin dira.
- **Erro-elementu bakarra** izan behar du.
- Etiketa baten izenak letra edo azpimarra batekin hasi behar du; ondorengo
  karaktereek zenbakiak izan ditzakete.
- **Prologoa** aukerakoa da, baina gomendagarria da bertsioa eta
  kodeketa adierazteko: `<?xml version="1.0" encoding="UTF-8"?>`.
- Konbentzioz, etiketa-izenak minuskulaz erabiltzen dira.
- Etiketa guztiak itxi behar dira.
- Atributuak komatxo artean joan behar dute.
- Elementuak zuzen habiaratu behar dira.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<liburutegia>
    <liburua id="1">
        <titulua>Cien años de soledad</titulua>
        <egilea>Gabriel García Márquez</egilea>
    </liburua>
</liburutegia>
```

## Dokumentu baten baliozkotasun mailak

1. **Gaizki formatua**: XMLren oinarrizko arauak urratzen ditu (itxi
   gabeko etiketak, baliozkoak ez diren karaktereak...).
2. **Ondo formatua**: XMLren sintaxi-arauak errespetatzen ditu.
3. **Baliozkoa**: ondo formatua dago **eta gainera** definitutako
   gramatika bat betetzen du (DTD bat edo XML Schema bat).

## Balidazioa: DTD eta XML Schema

XML DTD (*Document Type Definition*) baten edo XML Schema (XSD) baten
aurrean balida daiteke, egitura zehatz bat betetzen duela bermatzeko.

### DTD

DTD batek zein elementu eta atributu onartzen diren eta zein egiturarekin
formalizatzen du.

**Kuantifikatzaileak** (elementu bat zenbat aldiz ager daitekeen
adierazten dute):

| Ikurra | Esanahia |
|---|---|
| *(bat ere ez)* | zehazki behin |
| `?` | zero edo behin |
| `+` | behin edo gehiagotan |
| `*` | zero aldiz edo gehiagotan |

**Elementuen deklarazioa:**

```dtd
<!ELEMENT cliente (nombre, cif, diasentrega?)>
<!ELEMENT nombre (#PCDATA)>
<!ELEMENT cif (#PCDATA)>
```

Adibide honetan, `cliente` bakoitzak `nombre` eta `cif` eduki behar ditu
(biak nahitaezkoak), aukeran `diasentrega` jarraian dutela.

**Atributuen deklarazioa:**

```dtd
<!ATTLIST cantidad divisa CDATA #REQUIRED>
<!ATTLIST cantidad moneda CDATA #IMPLIED>
```

`#REQUIRED`-ek atributua nahitaezko bihurtzen du; `#IMPLIED`-ek aukerako
bihurtzen du.

**Ordenatutako sekuentzia** (`,`-z bereizitako elementuek ordena horretan
agertu behar dute):

```dtd
<!ELEMENT listaventas (ventapc+,ventamonitor+)>
```

Lehenik `ventapc` guztiak eta gero `ventamonitor` guztiak agertzea
eskatzen du.

**Edozein ordenatako aukera** (`|`-z bereizitako elementuak alternatiboak
dira):

```dtd
<!ELEMENT listaventas (ventapc|ventamonitor)+>
```

`ventapc` eta `ventamonitor` edozein ordenatan nahastuta onartzen ditu.

**Talde-alternatibak:**

```dtd
<!ELEMENT lista ((ventapc|ventamonitor)+|(comprapc|compramonitor)+)>
```

Salmenta-zerrenda bat edo erosketa-zerrenda bat onartzen du, baina ez bi
motak nahastea.

### XML Schema (XSD)

DTD bat baino ahaltsuagoa: XML formatuan bertan idazten da, datu-moten
balidazioa gehitzen du eta izen-espazioak (*namespaces*) onartzen ditu.

**Tipo sinpleak** (ez dute seme-elementurik ez atributurik onartzen):

- `xsd:integer`, `xsd:string`, `xsd:boolean`
- `xsd:date` (formatua: `UUUU-HH-EE`)
- `xsd:unsignedInt` (zenbaki oso positiboak bakarrik)
- `xsd:decimal` (zenbaki hamartarrak)

**Tipo konplexuak:**

- **Eduki sinplea**: testua gehi atributuak.
- **Eduki konplexua**: seme-elementuak eta/edo atributuak.

**Murrizketak** (onartutako balioak mugatzen dituzte):

```xml
<xsd:minInclusive value="16"/>
<xsd:maxInclusive value="65"/>
<xsd:pattern value="[A-Z]{2}[0-9]{2}[A-Z]{3}"/>
<xsd:enumeration value="euros"/>
```

**Hedapenak** (atributuak gehitzen dizkiote tipo sinple bati):

```xml
<xsd:complexType name="cantidad">
  <xsd:simpleContent>
    <xsd:extension base="xsd:float">
      <xsd:attribute name="divisa" use="required"/>
    </xsd:extension>
  </xsd:simpleContent>
</xsd:complexType>
```

**`sequence`** (elementuen ordena zehatz bat behartzen du):

```xml
<xsd:sequence>
  <xsd:element name="cif" type="xsd:string"/>
  <xsd:element name="nombre" type="xsd:string"/>
</xsd:sequence>
```

Agerpen-kontrola:

- `minOccurs="0"` — elementua aukerakoa bihurtzen du.
- `maxOccurs="unbounded"` — mugarik gabe errepikatzea baimentzen du.

**`choice`** (hainbaten artean aukera bakarra hautatzeko aukera ematen
du):

```xml
<xsd:choice>
  <xsd:element name="monitor"/>
  <xsd:element name="teclado"/>
</xsd:choice>
```

!!! tip "Patroi praktikoa"
    Elementu batek aldi berean testu-edukia eta atributuak behar
    dituenean, komeni da lehenik tipo sinple murriztu bat definitzea eta
    gero tipo konplexu baten barruan hedatzea. Bi urratseko planteamendu
    honek murrizketen eta hedapenen arteko gatazkak saihesten ditu.

Jarraitu [XSLT](../05-xslt/index.md) gaiarekin XML dokumentuak
eraldatzeko.
