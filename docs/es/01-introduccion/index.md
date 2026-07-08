# Introducción a los lenguajes de marcas

## ¿Qué es un lenguaje de marcas?

Un **lenguaje de marcas** (*markup language*) es un sistema de anotación que
combina texto con etiquetas (*tags*) que describen la estructura, el formato
o el significado semántico del contenido.

## Tipos principales

| Tipo | Ejemplos | Uso típico |
|---|---|---|
| Marcado de presentación | RTF | Definir formato visual |
| Marcado de procedimiento | LaTeX, troff | Instrucciones de procesado |
| Marcado descriptivo/semántico | HTML, XML | Describir la estructura del contenido |

Además de los lenguajes de marcas propiamente dichos existen otros formatos
de uso común:

- **LaTeX**: obliga a aprender su propia sintaxis de marcas, pero a cambio
  ofrece algoritmos muy sofisticados de maquetación de texto (por ejemplo,
  para fórmulas matemáticas).
- **Procesadores WYSIWYG** (*What You See Is What You Get*) como MS Word o
  LibreOffice Writer: son los más usados por el público general porque
  ocultan el marcado al usuario.
- **RTF**: mecanismo público que describe el aspecto de un documento y que
  puede implementarse libremente, sin pagar *royalties*.
- **PDF**: especificación liderada por Adobe, muy extendida para el
  intercambio de documentos con un formato fijo.
- **PostScript**: lenguaje abierto anterior al PDF; a diferencia de los
  anteriores no es solo descriptivo, sino un lenguaje de programación
  completo orientado a la impresión.

## Un poco de historia

**Pasado.** Los lenguajes de marcas tienen raíces antiguas, pero ganaron
popularidad real con la llegada de Internet. Su origen está en **SGML**
(*Standard Generalized Markup Language*), que nunca alcanzó una gran
audiencia pública aunque todavía se usa en contextos especializados. El
formato heredero más conocido hoy en día es **HTML** (*HyperText Markup
Language*).

**Presente.** HTML ha evolucionado mucho, siendo **HTML5** la versión
actual. Internet se sustenta sobre estándares abiertos e independientes de
cualquier tecnología o fabricante concreto, regulados de forma gratuita por
el W3C.

**Futuro.** La tendencia apunta a seguir con sistemas abiertos que fomenten
la competencia y beneficien a los usuarios. El crecimiento exponencial de la
web se debe en buena parte a los dispositivos móviles, que multiplican los
accesos a las páginas, aunque complican el diseño (de ahí la importancia del
diseño *responsive*).

## Servidores web

Un **servidor web** es un programa que entiende los protocolos HTTP/HTTPS y
responde a las peticiones de los navegadores. No necesita obligatoriamente
tener asociado un nombre de dominio.

Cuando se accede a una URL como `http://www.google.es`, el navegador
contacta con el programa servidor que se ejecuta en el equipo con ese
nombre, e intercambia información con él usando el protocolo HTTP.

**Funcionamiento básico:**

1. El servidor examina sus directorios en busca del recurso solicitado.
2. Si el fichero existe, lo transmite al cliente (código de respuesta
   **200**).
3. Si no existe, devuelve el conocido código de error **404** (recurso no
   encontrado).

**Tipos de servidor según dónde se aloja:**

- **Privados/domésticos**: ofrecen control absoluto sobre la máquina, pero
  mantener un ordenador encendido y conectado 24/7 es complicado, y las
  conexiones ADSL/fibra domésticas suelen tener limitaciones (sobre todo de
  subida) para servir un sitio con tráfico medio.
- **Alojados/alquilados**: tienen un coste que depende del espacio y del
  ancho de banda contratado, pero liberan al desarrollador de gestionar la
  infraestructura de red.

!!! note "Configurar un servidor web en casa (a grandes rasgos)"
    1. Instalar un servidor web (por ejemplo Apache, incluido en el paquete
       XAMPP) en un equipo.
    2. Anotar la IP local de ese equipo dentro de la red doméstica.
    3. Entrar en el router y abrir el puerto 80, redirigiendo el tráfico
       hacia esa IP local.
    4. Averiguar la IP pública del router (con un servicio tipo
       "WhatsMyIP").
    5. Compartir esa IP pública con quien deba acceder al servidor.
    6. Opcionalmente, alquilar un nombre de dominio y apuntarlo a la IP
       pública, para no depender de recordar números.

## Nombres de dominio

El sistema **DNS** (*Domain Name System*) traduce nombres fáciles de
recordar, como `www.loquesea.com`, a direcciones IP. Es un sistema complejo
que funciona de forma distribuida entre distintos países y organizaciones.

Los nombres de dominio se resuelven de derecha a izquierda (de la parte
final hacia el principio). La última parte se denomina **TLD** (*Top Level
Domain*, dominio de primer nivel: `.com`, `.es`, `.org`...), y cada uno está
administrado por una entidad (a menudo asociada a un país) que gestiona qué
nombres y marcas pueden registrarse dentro de su territorio.

## Sistemas de gestión de información (SGI)

Conceptos clave para entender qué es un SGI:

- **Sistema**: conjunto de elementos interrelacionados que colaboran para
  alcanzar un objetivo común.
- **Gestión**: conjunto de operaciones relevantes para las personas o las
  empresas.
- **Información**: datos que resultan útiles para desarrollar las funciones
  de una empresa u organización.

Un SGI **no requiere necesariamente estar informatizado**. Cuando sí lo
está, suele tratarse de programas adaptables a las necesidades de cada
empresa, capaces de importar y exportar datos con otros sistemas. Usar un
**formato unificado basado en marcas** (como XML) facilita enormemente esa
transferencia de datos entre sistemas distintos.

## Organismos de regulación

- **W3C** (*World Wide Web Consortium*): estandariza HTML, CSS, XML...
  Publica sus estándares como *Technical Recommendations* (TR), de descarga
  gratuita, para garantizar la interoperabilidad de la web.
- **WHATWG**: mantiene el estándar HTML como *living standard* (en
  evolución continua).
- **ISO** (*International Standards Organization*): emite estándares
  también aplicables a la documentación y al intercambio de información.

## Gramáticas, DTDs y XML Schemas

Toda gramática de un lenguaje de marcas especifica qué es válido y qué no.
Es recomendable respetar la gramática elegida al escribir un documento. Por
ejemplo, este es un documento HTML5 válido:

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Page Title</title>
    </head>
    <body>
        Mi primera página
    </body>
</html>
```

**Evolución de las versiones de HTML:**

- **HTML4**: gramática muy permisiva, lo que dificultaba que los
  navegadores procesaran el HTML de forma consistente entre ellos.
- **XHTML**: reescritura de HTML con las reglas estrictas de XML (todo debe
  cerrarse, anidarse correctamente, etc.), lo que simplificó el trabajo de
  los navegadores.
- **HTML5**: evolución de XHTML que añade, entre otras cosas, etiquetas
  como `<audio>` y `<video>` y amplía notablemente las capacidades de
  JavaScript en el navegador.

Una **DTD** (*Document Type Definition*) especifica qué estructura puede
tener un documento de marcas. Ejemplo:

```dtd
<!ELEMENT lista_de_personas (persona*)>
<!ELEMENT persona (nombre, fechanacimiento?, sexo?, numeroseguridadsocial?)>
<!ELEMENT nombre (#PCDATA)>
```

Los **XML Schema (XSD)** surgieron para resolver imprecisiones de las DTD:
permiten definir la estructura de un documento con mucha más precisión (por
ejemplo, tipos de datos concretos), a costa de una sintaxis más compleja.
Ejemplo:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <xsd:element name="Libro">
        <xsd:complexType>
            <xsd:sequence>
                <xsd:element name="Título" type="xsd:string"/>
                <xsd:element name="Autores" type="xsd:string" maxOccurs="10"/>
            </xsd:sequence>
        </xsd:complexType>
    </xsd:element>
</xsd:schema>
```

## Definiciones fundamentales

- **Etiqueta**: secuencia de texto comprendida entre `<` y `>`.
- **Elemento**: todo el contenido comprendido entre una etiqueta de
  apertura y su correspondiente etiqueta de cierre, incluyendo los
  subelementos que contenga.
- **Atributo**: texto que acompaña a una etiqueta y que amplía la
  información sobre ella (por ejemplo `id`, `class`, `href`...).
- **Árbol del documento / DOM**: representación jerárquica de un documento
  XML o HTML5 que puede recorrerse desde un lenguaje de programación.
- **Relaciones de parentesco en el DOM**: un nodo **hijo** aparece más
  abajo en el árbol que su nodo **padre**; los nodos **hermanos** son
  aquellos que se encuentran en el mismo nivel del árbol.

## Próximos pasos

Continúa con [HTML](../02-html/index.md) o [XML](../04-xml/index.md).
