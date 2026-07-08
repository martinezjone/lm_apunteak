# Marka lengoaien sarrera

## Zer da marka lengoaia bat?

**Marka lengoaia** bat (*markup language*) testua eta etiketak (*tags*)
konbinatzen dituen anotazio-sistema bat da; etiketa horiek edukiaren
egitura, formatua edo esanahi semantikoa deskribatzen dute.

## Mota nagusiak

| Mota | Adibideak | Erabilera tipikoa |
|---|---|---|
| Aurkezpen-marka | RTF | Itxura bisuala definitzea |
| Prozedura-marka | LaTeX, troff | Prozesatze-argibideak |
| Marka deskribatzailea/semantikoa | HTML, XML | Edukiaren egitura deskribatzea |

- **Aurkezpenera Bideratuak**: Testuaren formatua (itxura) definitzen du. Hauek etiketak ezkutatu eta erabiltzaileari testua bakarrik erakusten diote formatuarekin.  
  *Adib.:* **RTF**

- **Prozedurazko bideratuak**: Aurkezpenera ere bideratuta dago, baina, gainera, dokumentuaren programak (Nabigatzailea, konpilatzailea) etiketak interpretatu behar ditu, etiketen arabera ekintzak egiteko.  
  *Adib.:* **HTML**, **LaTeX**

- **Deskribatzaileak**: Dokumentuaren egituraren atalak deskribatzen dituzte, hau da, edukia definitzen dute, baina ez dute zehazten nola irudikatu behar diren.  
  *Adib.:* **XML**

## Historia pixka bat

**Iragana.** Marka-lengoaiak dokumentuen egitura eta formatua deskribatzeko sortu ziren. 1960ko hamarkadan informazioa aplikazio desberdinen artean trukatzeko beharra agertu zen, eta 1970ean IBMk **GML** (*Generalized Markup Language*) garatu zuen. Hortik sortu zen 1986an **SGML** (*Standard Generalized Markup Language*), marka-lengoaien oinarria bihurtu zena. 1989an, **Tim Berners-Lee**k SGMLn oinarrituta **HTML** sortu zuen, World Wide Weberako.

**Oraina.** 1990eko hamarkadan **W3C** (*World Wide Web Consortium*) sortu zen webaren estandarrak garatzeko, eta 1998an **XML** estandarra argitaratu zuen, datuak deskribatzeko. Bien bitartean, HTML etengabe eboluzionatu da, eta gaur egun **HTML5** da bertsio nagusia: multimedia, web aplikazioak eta eduki semantikoa modu estandar eta irekian onartzen ditu.

**Etorkizuna.** Webak estandar irekietan oinarritzen jarraituko du, gailu eta plataforma guztietan bateragarritasuna bermatzeko. Gainera, web aplikazioak gero eta aberatsagoak izango dira, irisgarritasuna, errendimendua eta diseinu *responsive*-a gero eta garrantzitsuagoak bihurtuz.

## Ezaugarriak

Markaketa-lengoaiek hainbat ezaugarri dituzte, dokumentuak sortu, irakurri eta trukatzeko oso egokiak egiten dituztenak.

### Testu laua

- Dokumentuak **testu hutsez** osatuta daude; ez dute formatu bitarrik.
- Edozein testu-editorekin ireki eta editatu daitezke.
- Plataforma eta sistema eragile guztietan bateragarriak dira.

### Prozesatzeko erraztasuna

- Etiketen egitura dela eta, programentzat erraz interpretatzeko modukoak dira.
- Dokumentuak automatikoki balioztatu, eraldatu edo prozesatu daitezke.

### Malgutasuna

- Hasieran testu-dokumentuak deskribatzeko sortu baziren ere, gaur egun webguneetan, web-zerbitzuetan, konfigurazio-fitxategietan eta datuen trukean erabiltzen dira.
- Behar bakoitzerako markaketa-lengoaia desberdinak daude (HTML, XML...).
- Dokumentu berean hainbat teknologia konbina daitezke (adibidez, HTML, CSS eta JavaScript).

## Erakundeak eta estandarrak

Webaren garapena posible izan da estandar irekiak definitzen dituzten erakundeei esker. Garrantzitsuenak hauek dira:

### W3C (*World Wide Web Consortium*)

- 1994an **Tim Berners-Lee**k sortu zuen.
- Webaren estandarrak garatu eta mantentzen ditu.
- Bere helburua web unibertsala, irisgarria eta bateragarria bermatzea da.
- HTML, CSS eta beste web-estandar askoren garapena koordinatzen du.

[www.w3.org](https://www.w3.org/){: target="_blank" rel="noopener" }

[www.w3schools.com](https://www.w3schools.com/html/default.asp){: target="_blank" rel="noopener" }

### ISO (*International Organization for Standardization*)

- Nazioarteko estandarizazio-erakundea da.
- Industria eta teknologia arlo askotan estandarrak definitzen ditu.
- 1986an **SGML** nazioarteko estandar gisa onartu zuen (ISO 8879).


# Webaren oinarriak

## Zer da Weba?

**World Wide Web (WWW)** Interneten barruan dagoen zerbitzu bat da.

Weba elkarri esteken bidez lotutako dokumentuen eta baliabideen multzoa da.

Dokumentu horiei **web-orriak** deitzen diegu.


## Zer da webgune bat?

Webgune bat elkar lotutako web-orrien multzoa da.

Normalean atal desberdinak ditu:

- Hasiera
- Guri buruz
- Kontaktua
- Produktuak
- Bloga...


## Web-orri baten osagaiak

Web-orri batek baliabide desberdinak izan ditzake:

- HTML (egitura)
- CSS (itxura)
- JavaScript (portaera)
- Irudiak
- Bideoak
- Audioak
- Beste fitxategi batzuk


## Webgune bat nola sortzen da?

Normalean urrats hauek jarraitzen dira:

1. Helburua definitu.
2. Edukiak planifikatu.
3. Gunearen egitura diseinatu.
4. HTML bidez orriak sortu.
5. CSS bidez diseinua gehitu.
6. JavaScript bidez funtzionaltasunak gehitu (beharrezkoa bada).
7. Web zerbitzari batean argitaratu.



## Webgune motak: estatikoak eta dinamikoak

- **Webgune estatikoa**: orri guztiak aldez aurretik sortuta daude (HTML,
  CSS eta JavaScript fitxategi solteak) eta zerbitzariak fitxategi horiek
  aldatu gabe bidaltzen ditu. Edukia eguneratzeko, fitxategiak eskuz
  aldatu behar dira.
- **Webgune dinamikoa**: orriak eskaera bakoitzean zerbitzarian sortzen
  dira, normalean datu-base batekin (adibidez MySQL) eta programazio-
  lengoaia batekin (PHP, JavaScript...) konbinatuta. Horri esker edukia
  erraz kudeatu daiteke programatu gabe, hain zuzen ere **CMS** batzuek
  (WordPress bezala) egiten duten moduan.

Modulu honetan bien adibideak landuko ditugu: HTML/CSS/JavaScript
hutsezko webgune estatikoak, eta WordPress bezalako CMS baten bidez
sortutako webgune dinamikoak.

## Web garatzeko tresnak

Webgune bat sortzeko normalean honako tresnak erabiltzen dira:

- Testu-editorea (Visual Studio Code...)
- Nabigatzailea (Chrome, Firefox...)
- Irudi-editorea (GIMP...)
- Web zerbitzaria (Apache, Nginx, XAMPP...)
- FTP edo Git fitxategiak argitaratzeko



## Web zerbitzaria

Web zerbitzari bat web-orriak gordetzen dituen eta nabigatzaileei bidaltzen dizkien programa da.

Nabigatzaile batek webgune batera sartzen denean:

1. HTTP eskaera bidaltzen du.
2. Zerbitzariak fitxategia bilatzen du.
3. Aurkitzen badu, bidaltzen du (**200 OK**).
4. Aurkitzen ez badu, **404 Not Found** erantzuten du.

Gaur egun **HTTPS** (HTTP segurua) da estandarra: HTTPri zifratze-geruza
bat gehitzen dio ziurtagiri **SSL/TLS** baten bidez, nabigatzailearen eta
zerbitzariaren arteko informazioa (pasahitzak, datu pertsonalak...) inork
bidean irakurri edo aldatu ez dezan. Nabigatzaileek giltzarrapo-ikono
batekin adierazten dute konexioa segurua dela.



## Domeinu-izenak eta DNS

Normalean ez ditugu IP helbideak erabiltzen, baizik eta domeinu-izenak.

Adibidez:

- `www.ehu.eus`
- `www.google.com`

**DNS** sistemak domeinu-izen horiek dagokien IP helbidera itzultzen ditu.

Azken zatia **TLD** (*Top Level Domain*) da:

- `.com`
- `.org`
- `.es`
- `.eus`

## URLaren anatomia

**URL** batek (*Uniform Resource Locator*) baliabide bat non dagoen eta
nola atzitu adierazten du. Adibidez:

`https://www.ehu.eus/eu/produktuak?kategoria=liburuak`

- **Protokoloa** (`https://`): nabigatzaileak eta zerbitzariak nola
  komunikatuko diren adierazten du.
- **Domeinua** (`www.ehu.eus`): zerbitzaria identifikatzen duen izena.
- **Bidea** (`/eu/produktuak`): zerbitzariaren barruan baliabidea non
  dagoen adierazten du.
- **Kontsulta-parametroak** (`?kategoria=liburuak`): informazio
  gehigarria, `?` ikurraren ondoren `parametroa=balioa` bikoteetan
  adierazita; `&` erabiltzen da parametro bat baino gehiago badaude.

Hurrengo gaian **HTML** dokumentu bat sortzen hasiko gara.

## Hurrengo urratsak

Jarraitu [HTML](../02-html/index.md) edo [XML](../04-xml/index.md)
gaiekin.
