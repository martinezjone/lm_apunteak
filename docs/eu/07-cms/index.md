# CMS (Eduki Kudeaketa Sistemak)

## Zer da CMS bat?

**CMS** bat (*Content Management System*, Eduki Kudeaketa Sistema) web
orri batean edukia sortu, editatu, antolatu eta argitaratzeko aukera
ematen duen web aplikazio bat da, **programatu beharrik gabe**. Edukia
(testuak, irudiak, produktuak...) aurkezpenetik (txantiloia edo gai
bisuala) bereizten du, era honetan eduki berbera diseinu ezberdinekin
erakuts daiteke, eta hainbat pertsonak informazioa kudeatu dezakete
kodea ukitu gabe.

Abantaila nagusiak:

- Ez du programazio-ezagutza aurreraturik behar edukia argitaratzeko.
- Diseinua (gaiak/txantiloiak) datuetatik bereizten du.
- Funtzionalitateak zabaltzeko aukera ematen du osagarrien/hedapenen
  bidez (*plugins*).
- Lan kolaboratiboa errazten du (rol ezberdinak dituzten hainbat
  erabiltzaile: administratzailea, editorea, egilea...).
- Erabiltzaile-kudeaketa, iruzkinak, SEOa eta multimedia jatorriz izan
  ohi ditu.

## Gaur egun gehien erabiltzen diren CMSak

| CMS | Lengoaia | Erabilera tipikoa |
|---|---|---|
| **WordPress** | PHP | Blogak, enpresa-webguneak, online dendak (WooCommerce-rekin) |
| **Joomla** | PHP | Enpresa-webguneak eta konplexutasun ertaineko atariak |
| **Drupal** | PHP | Tamaina handiko eta pertsonalizazio altuko webguneak |
| **Shopify** | Jabeduna (SaaS) | Online dendak (ecommerce) |
| **Wix** | Jabeduna (SaaS) | Instalaziorik gabeko web erraz guztiak, hodeian |
| **Magento (Adobe Commerce)** | PHP | Bolumen handiko online dendak |

**WordPress** da, alde handiz, hedatuena dagoen CMSa: Interneteko web
orri guztien %40-45 inguru mugitzen duela kalkulatzen da. Bere
herrikoitasunagatik, komunitateagatik eta erabiltzeko errazatasunagatik,
modulu honetan zentratuko garen CMSa izango da.

## WordPress

### WordPress-en bi bertsioak

Ohikoa da izen bera partekatzen duten bi produktu ezberdin nahastea:

- **WordPress.org**: **kode irekiko** softwarea, doan deskargatzen dena
  eta zerbitzari propio batean instalatzen dena (hemendik aurrera,
  "WordPress"-i buruz hitz egiten dugunean, honi buruz izango da).
- **WordPress.com**: Automattic-ek kudeatutako **ostalaritza-zerbitzu**
  bat, software bera erabiltzen duena, baina aukera gratuito mugatuekin
  eta funtzio gehiagorako ordainpeko planekin.

### Orrialde ofizialak

- **wordpress.org**: software libreko proiektuaren gune ofiziala. Hemen
  aurkitzen dira CMSaren deskarga, gaien biltegi ofiziala, pluginen
  biltegi ofiziala eta dokumentazio teknikoa.
- **wordpress.com**: kudeatutako ostalaritza-zerbitzuaren atari.

### Non deskargatu

Instalazio-paketea **wordpress.org**-eko deskarga-atalean deskargatzen
da, `.zip` (edo `.tar.gz`) formatuan, eta CMSaren funtzionamendurako
beharrezkoak diren PHP fitxategi guztiak dauzka.

!!! note "Aurretiko baldintzak"
    WordPressek **PHP** duen zerbitzari bat eta **MySQL** edo
    **MariaDB** datu-base bat behar ditu, gehi **Apache** edo **Nginx**
    bezalako web zerbitzari bat. Horregatik, tokian instalatzeko, hori
    guztia aurrekonfiguratuta duen pakete bat erabiliko dugu: **MAMP**.

## WordPress MAMPen instalatzea

**MAMP** (*My Apache MySQL PHP*) Windows eta macOSerako eskuragarri
dagoen tokiko zerbitzari-pakete bat da, Apache, MySQL eta PHP batera
instalatzen dituena, zerbitzuak abiarazteko eta gelditzeko kontrol-panel
grafiko batekin batera. XAMPPen baliokidea da, baina beste fabrikatzaile
batek garatua.

### Instalazio-urratsak

1. **MAMP instalatu**: MAMP-en webgune ofizialetik instalatzailea
   deskargatu eta exekutatu, lehenetsitako aukerak onartuz.
2. **Zerbitzariak abiarazi**: MAMPen kontrol-panela ireki eta **Start
   Servers** sakatu Apache eta MySQL abiarazteko. Adierazle berde batek
   bi zerbitzuak aktibo daudela baieztatzen du.
3. **Datu-basea sortu**: MAMPen paneletik, **phpMyAdmin** ireki (MySQL
   kudeatzeko web-tresna) eta datu-base berri bat sortu, adibidez
   `wordpress`, `utf8mb4_unicode_ci` cotejamenduarekin.
4. **WordPress deskargatu eta deskonprimitu**: `.zip` fitxategia
   wordpress.org-etik deskargatu eta MAMPek web-erro gisa erabiltzen
   duen karpetan deskonprimitu (`htdocs` Windowsen, edo macOSen
   **Preferences → Web Server → Document Root**-en konfiguratutako
   karpeta).
5. **Instalazio-laguntzailera sartu**: zerbitzariak abiarazita
   daudela, nabigatzailea MAMPek adierazten duen tokiko URLan ireki
   (lehenespenez `http://localhost:8888/wordpress` antzeko zerbait,
   MAMPek 8888 ataka erabili ohi baitu Apacherako 80aren ordez).
6. **Datu-basearekiko konexioa konfiguratu**: laguntzaileak hauek
   eskatuko ditu:
     - Datu-basearen izena (3. urratsean sortutakoa).
     - MySQL erabiltzailea eta pasahitza (MAMPen lehenespenez `root` /
       `root` izan ohi dira).
     - Datu-basearen zerbitzaria (normalean `localhost:8889`, MAMPek
       MySQLren lehenetsitako ataka ere aldatzen baitu).
7. **WordPressen laguntzailea osatu**: gunearen titulua adierazi,
   erabiltzaile administratzailea sortu (izena, pasahitza, emaila) eta
   instalazioa amaitu.
8. **Administrazio-panelera sartu**: instalatu ondoren, administrazio-
   mahaigaina `/wp-admin`-en eskuragarri dago, adibidez
   `http://localhost:8888/wordpress/wp-admin`.

!!! tip "Datu erabilgarria"
    Laguntzaileak `wp-config.php` fitxategia aurkitzen ez badu,
    automatikoki sortzen du `wp-config-sample.php`-tik abiatuta, 6.
    urratsean sartutako datuekin. Fitxategi hori eskuz ere sortu eta
    editatu daiteke laguntzailea exekutatu aurretik, `DB_NAME`,
    `DB_USER`, `DB_PASSWORD` eta `DB_HOST` adieraziz.
