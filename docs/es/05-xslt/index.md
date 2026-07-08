# XSLT

## ¿Qué es XSLT?

**XSLT** (*eXtensible Stylesheet Language Transformations*) es un lenguaje
declarativo para transformar documentos XML en otros formatos (HTML, texto,
otro XML...).

## Ejemplo básico

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

## Conceptos clave

- `<xsl:template>`: define una plantilla de transformación.
- `<xsl:value-of>`: extrae el valor de un nodo.
- `<xsl:for-each>`: itera sobre un conjunto de nodos.
