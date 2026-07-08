# XML

## ¿Qué es XML?

**XML** (*eXtensible Markup Language*) es un lenguaje de marcas diseñado para
almacenar y transportar datos de forma estructurada y legible tanto por
humanos como por máquinas.

A diferencia de HTML, que tiene un propósito fijo y un conjunto cerrado de
etiquetas, XML permite crear **lenguajes de marcas propios** (vocabularios)
definidos por el propio usuario, pensados para el intercambio de datos
entre programas.

## Reglas de construcción

- **Distingue mayúsculas de minúsculas**: `<cliente>`, `<Cliente>` y
  `<CLIENTE>` son tres etiquetas distintas.
- Debe tener un **único elemento raíz**.
- El nombre de una etiqueta debe empezar por letra o guion bajo; los
  caracteres siguientes sí pueden incluir números.
- El **prólogo** es opcional, pero se recomienda incluirlo para indicar la
  versión y la codificación: `<?xml version="1.0" encoding="UTF-8"?>`.
- Por convención se usan nombres de etiqueta en minúsculas.
- Todas las etiquetas deben cerrarse.
- Los atributos deben ir entre comillas.
- Los elementos deben anidarse correctamente.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<biblioteca>
    <libro id="1">
        <titulo>Cien años de soledad</titulo>
        <autor>Gabriel García Márquez</autor>
    </libro>
</biblioteca>
```

## Niveles de validez de un documento

1. **Mal formado**: incumple las reglas básicas de XML (etiquetas sin
   cerrar, caracteres no válidos...).
2. **Bien formado**: respeta las reglas de sintaxis de XML.
3. **Válido**: está bien formado **y además** cumple una gramática
   definida (una DTD o un XML Schema).

## Validación: DTD y XML Schema

XML puede validarse frente a una **DTD** (*Document Type Definition*) o un
**XML Schema (XSD)** para garantizar que cumple una estructura determinada.

### DTD

Una DTD formaliza qué elementos y atributos están permitidos y con qué
estructura.

**Cuantificadores** (indican cuántas veces puede aparecer un elemento):

| Símbolo | Significado |
|---|---|
| *(ninguno)* | exactamente una vez |
| `?` | cero o una vez |
| `+` | una o más veces |
| `*` | cero o más veces |

**Declaración de elementos:**

```dtd
<!ELEMENT cliente (nombre, cif, diasentrega?)>
<!ELEMENT nombre (#PCDATA)>
<!ELEMENT cif (#PCDATA)>
```

En este ejemplo, todo `cliente` debe contener `nombre` y `cif` (ambos
obligatorios), seguidos opcionalmente de `diasentrega`.

**Declaración de atributos:**

```dtd
<!ATTLIST cantidad divisa CDATA #REQUIRED>
<!ATTLIST cantidad moneda CDATA #IMPLIED>
```

`#REQUIRED` hace que el atributo sea obligatorio; `#IMPLIED` lo hace
opcional.

**Secuencia con orden** (los elementos separados por `,` deben aparecer en
ese orden):

```dtd
<!ELEMENT listaventas (ventapc+,ventamonitor+)>
```

Exige que aparezcan primero todos los `ventapc` y después todos los
`ventamonitor`.

**Elección en cualquier orden** (los elementos separados por `|` son
alternativos):

```dtd
<!ELEMENT listaventas (ventapc|ventamonitor)+>
```

Permite `ventapc` y `ventamonitor` mezclados en cualquier orden.

**Alternativas agrupadas:**

```dtd
<!ELEMENT lista ((ventapc|ventamonitor)+|(comprapc|compramonitor)+)>
```

Permite o bien una lista de ventas, o bien una lista de compras, pero no
mezclar ambos tipos.

### XML Schema (XSD)

Más potente que una DTD: se escribe en el propio formato XML, incorpora
validación de tipos de datos y soporta espacios de nombres (*namespaces*).

**Tipos simples** (no admiten elementos hijos ni atributos):

- `xsd:integer`, `xsd:string`, `xsd:boolean`
- `xsd:date` (formato `AAAA-MM-DD`)
- `xsd:unsignedInt` (solo números enteros positivos)
- `xsd:decimal` (números con decimales)

**Tipos complejos:**

- **Contenido simple**: texto más atributos.
- **Contenido complejo**: elementos hijos y/o atributos.

**Restricciones** (limitan los valores permitidos):

```xml
<xsd:minInclusive value="16"/>
<xsd:maxInclusive value="65"/>
<xsd:pattern value="[A-Z]{2}[0-9]{2}[A-Z]{3}"/>
<xsd:enumeration value="euros"/>
```

**Extensiones** (añaden atributos a un tipo simple):

```xml
<xsd:complexType name="cantidad">
  <xsd:simpleContent>
    <xsd:extension base="xsd:float">
      <xsd:attribute name="divisa" use="required"/>
    </xsd:extension>
  </xsd:simpleContent>
</xsd:complexType>
```

**`sequence`** (obliga a un orden concreto de los elementos):

```xml
<xsd:sequence>
  <xsd:element name="cif" type="xsd:string"/>
  <xsd:element name="nombre" type="xsd:string"/>
</xsd:sequence>
```

Control de ocurrencias:

- `minOccurs="0"` — hace el elemento opcional.
- `maxOccurs="unbounded"` — permite repetirlo sin límite.

**`choice`** (permite elegir una única alternativa entre varias):

```xml
<xsd:choice>
  <xsd:element name="monitor"/>
  <xsd:element name="teclado"/>
</xsd:choice>
```

!!! tip "Patrón práctico"
    Cuando un elemento necesita a la vez contenido de texto y atributos,
    conviene definir primero un tipo simple restringido y luego
    extenderlo dentro de un tipo complejo. Este enfoque en dos pasos evita
    conflictos entre restricciones y extensiones.

Continúa con [XSLT](../05-xslt/index.md) para transformar documentos XML.
