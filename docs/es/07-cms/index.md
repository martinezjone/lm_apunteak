# CMS (Sistemas de Gestión de Contenidos)

## ¿Qué es un CMS?

Un **CMS** (*Content Management System*, Sistema de Gestión de
Contenidos) es una aplicación web que permite crear, editar, organizar y
publicar contenido en una página web **sin necesidad de programar**.
Separa el contenido (textos, imágenes, productos...) de la presentación
(la plantilla o tema visual), de forma que un mismo contenido puede
mostrarse con diseños distintos, y varias personas pueden gestionar la
información sin tocar código.

Ventajas principales:

- No requiere conocimientos avanzados de programación para publicar
  contenido.
- Separa el diseño (temas/plantillas) de los datos.
- Permite ampliar funcionalidades mediante complementos/extensiones
  (*plugins*).
- Facilita el trabajo colaborativo (varios usuarios con distintos roles:
  administrador, editor, autor...).
- Suele incluir gestión de usuarios, comentarios, SEO y multimedia de
  serie.

## CMS más utilizados hoy en día

| CMS | Lenguaje | Uso típico |
|---|---|---|
| **WordPress** | PHP | Blogs, webs corporativas, tiendas online (con WooCommerce) |
| **Joomla** | PHP | Webs corporativas y portales de mediana complejidad |
| **Drupal** | PHP | Webs de gran tamaño y alta personalización |
| **Shopify** | Propietario (SaaS) | Tiendas online (ecommerce) |
| **Wix** | Propietario (SaaS) | Webs sencillas sin instalación, todo en la nube |
| **Magento (Adobe Commerce)** | PHP | Tiendas online de gran volumen |

**WordPress** es, con diferencia, el CMS más extendido: se estima que
mueve en torno al 40-45% de todas las páginas web de Internet. Por su
popularidad, comunidad y facilidad de uso, será el CMS en el que nos
centraremos en este módulo.

## WordPress

### Dos versiones de WordPress

Es habitual confundir dos productos distintos que comparten nombre:

- **WordPress.org**: el software **de código abierto**, que se descarga
  gratuitamente y se instala en un servidor propio (de aquí en adelante,
  cuando hablemos de "WordPress" nos referiremos a este).
- **WordPress.com**: un **servicio de alojamiento** gestionado por
  Automattic que usa ese mismo software, pero con opciones gratuitas
  limitadas y planes de pago para más funciones.

### Páginas oficiales

- **wordpress.org**: sitio oficial del proyecto de software libre. Aquí
  se encuentra la descarga del CMS, el repositorio oficial de temas,
  el repositorio oficial de plugins y la documentación técnica.
- **wordpress.com**: portal del servicio de alojamiento gestionado.

### Dónde descargarlo

El paquete de instalación se descarga desde la sección de descargas de
**wordpress.org**, en formato `.zip` (o `.tar.gz`), y contiene todos los
ficheros PHP necesarios para el funcionamiento del CMS.

!!! note "Requisitos previos"
    WordPress necesita un servidor con **PHP** y una base de datos
    **MySQL** o **MariaDB**, además de un servidor web como **Apache** o
    **Nginx**. Por eso, para instalarlo en local, usaremos un paquete que
    ya incluye todo esto preconfigurado: **MAMP**.

## Instalación de WordPress en MAMP

**MAMP** (*My Apache MySQL PHP*) es un paquete de servidor local
disponible para Windows y macOS que instala de forma conjunta Apache,
MySQL y PHP, junto con un panel de control gráfico para arrancar y
detener los servicios. Es el equivalente a XAMPP, pero desarrollado por
otro fabricante.

### Pasos de instalación

1. **Instalar MAMP**: descargar el instalador desde la web oficial de
   MAMP y ejecutarlo, aceptando las opciones por defecto.
2. **Arrancar los servidores**: abrir el panel de control de MAMP y
   pulsar **Start Servers** para arrancar Apache y MySQL. Un indicador
   en verde confirma que ambos servicios están activos.
3. **Crear la base de datos**: desde el panel de MAMP, abrir
   **phpMyAdmin** (herramienta web de gestión de MySQL) y crear una base
   de datos nueva, por ejemplo `wordpress`, con cotejamiento
   `utf8mb4_unicode_ci`.
4. **Descargar y descomprimir WordPress**: descargar el `.zip` desde
   wordpress.org y descomprimirlo dentro de la carpeta que MAMP usa como
   raíz web (`htdocs` en Windows, o la carpeta configurada en
   **Preferences → Web Server → Document Root** en macOS).
5. **Acceder al asistente de instalación**: con los servidores
   arrancados, abrir el navegador en la URL local que indique MAMP
   (por defecto algo como `http://localhost:8888/wordpress`, ya que MAMP
   suele usar el puerto 8888 para Apache en lugar del 80).
6. **Configurar la conexión a la base de datos**: el asistente pedirá:
     - Nombre de la base de datos (la creada en el paso 3).
     - Usuario y contraseña de MySQL (por defecto en MAMP suelen ser
       `root` / `root`).
     - Servidor de la base de datos (normalmente `localhost:8889`, ya
       que MAMP también cambia el puerto por defecto de MySQL).
7. **Completar el asistente de WordPress**: indicar el título del sitio,
   crear el usuario administrador (nombre, contraseña, email) y finalizar
   la instalación.
8. **Acceder al panel de administración**: una vez instalado, el
   escritorio de administración está disponible en `/wp-admin`, por
   ejemplo `http://localhost:8888/wordpress/wp-admin`.

!!! tip "Dato útil"
    Si el asistente no encuentra el fichero `wp-config.php`, lo genera
    automáticamente a partir de `wp-config-sample.php` con los datos que
    introduzcas en el paso 6. También se puede crear y editar ese fichero
    a mano antes de ejecutar el asistente, indicando `DB_NAME`,
    `DB_USER`, `DB_PASSWORD` y `DB_HOST`.
