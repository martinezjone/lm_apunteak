# Otra forma de maquetar 

Hemos conocido como usar felx para maquetar nuestras páginas web, ahora vamos a ver otra  forma diferente e igual de eficaz


## Grid

CSS Grid se usa para organizar elementos en **filas y columnas**.

``` css
.edukiontzia {
    display: grid;
}
```

Por ejemplo, para crear tres columnas iguales:

``` css
.edukiontzia {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
}
```

Forma más breve:

``` css
.edukiontzia {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}
```

Espacio entre los elementos:

``` css
.edukiontzia {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

!!! note "La unidad `fr`"

    `fr` es una unidad de Grid que representa una fracción del espacio disponible.

    Al usar `1fr 1fr 1fr`, el espacio se divide en tres partes iguales.
