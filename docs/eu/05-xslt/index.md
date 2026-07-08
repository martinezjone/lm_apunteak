# XSLT

## Zer da XSLT?

**XSLT** (*eXtensible Stylesheet Language Transformations*) XML
dokumentuak beste formatu batzuetara eraldatzeko lengoaia deklaratibo bat
da (HTML, testua, beste XML bat...).

## Oinarrizko adibidea

```xml
<?xml version="1.0" encoding="UTF-8"?>
<xsl:stylesheet version="1.0"
    xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
  <xsl:template match="/">
    <html>
      <body>
        <h1><xsl:value-of select="biblioteca/libro/titulo"/></h1>
      </body>
    </html>
  </xsl:template>
</xsl:stylesheet>
```

## Kontzeptu gakoak

- `<xsl:template>`: eraldaketa-txantiloi bat definitzen du.
- `<xsl:value-of>`: nodo baten balioa ateratzen du.
- `<xsl:for-each>`: nodo-multzo baten gainean iteratzen du.
