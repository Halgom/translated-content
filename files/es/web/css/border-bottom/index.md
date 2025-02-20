---
title: border-bottom
slug: Web/CSS/border-bottom
tags:
  - CSS
  - CSS:Referencias
  - Todas_las_Categorías
translation_of: Web/CSS/border-bottom
---
<< [Volver](/es/Guía_de_referencia_de_CSS)

### Resumen

La propiedad `border-bottom` permite de definir de una vez todas las propiedades individuales {{ Cssxref("border-bottom-color") }}, {{ Cssxref("border-bottom-style") }}, y {{ Cssxref("border-bottom-width") }}, las cuales describen el color, estilo y ancho del borde inferior de un elementos.

- {{ Cssxref("initial", "Valor inicial") }}: ver propiedades individuales
- Se aplica a : todos los elementos
- {{ Cssxref("inheritance", "Valor heredado") }}: no
- Porcentajes: N/A
- Medio: {{ Xref_cssvisual() }}
- {{ Cssxref("computed value", "Valor calculado") }}: ver propiedades individuales

### Sintaxis

```
border-bottom: [ <border-width> || <border-style> || <border-color> ] | inherit
```

### Valores

- \<border-width>
  - : ver {{ Cssxref("border-bottom-width") }}.
- \<border-style>
  - : ver {{ Cssxref("border-bottom-style") }}.
- \<border-color>
  - : ver {{ Cssxref("border-bottom-color") }}.

### Ejemplos

[Ver El Ejemplo Vivo](/samples/cssref/border.html)

```
element {
    border-bottom-width: 1px solid #000;
}
```

### Notas

Si no se especifica el color del borde, este tomará el valor definido en la propiedad del {{ Cssxref("color") }} general.

Se puede especificar los tres valores en cualquier orden y se pueden omitir una o dos.

Como con todas las propiedades generales, `border-bottom` siempre inicia todos los valores que le pueden ser definidos aún cuando no están especificados, en este caso toma los valores por defecto.

Lo que significa que:

```
  border-bottom-style: dotted;
  border-bottom: thick green;
```

es idéntico a:

```
  border-bottom-style: dotted;
  border-bottom: none thick green;
```

y el valor de {{ Cssxref("border-bottom-style") }} dado antes de `border-bottom` es ignorado.

Como el valor por defecto de {{ Cssxref("border-bottom-style") }} es `none`, el no especificar la parte \<border-style> en la propiedad general significa: **sin borde**.

### Especificaciones

- [CSS 1](http://www.w3.org/TR/CSS1#border-bottom)
- [CSS 2.1](http://www.w3.org/TR/CSS21/box.html#border-shorthand-properties)
- [CSS 3](http://www.w3.org/TR/css3-background/#the-border-shorthands)

### Compatibilidades

| Navegador         | Versión mínima |
| ----------------- | -------------- |
| Internet Explorer | 4              |
| Firefox           | 1              |
| Netscape          | 4              |
| Opera             | 3.5            |

### Ver también

{{ Cssxref("border") }}, {{ Cssxref("border-bottom") }}, {{ Cssxref("border-bottom-width") }}, {{ Cssxref("border-bottom-style") }}, {{ Cssxref("border-bottom-color") }},

Categorías

Interwiki Languages

{{ languages( { "de": "de/CSS/border-bottom", "en": "en/CSS/border-bottom", "fr": "fr/CSS/border-bottom", "ja": "ja/CSS/border-bottom", "pl": "pl/CSS/border-bottom" } ) }}
