---
title: ':indeterminate'
slug: Web/CSS/:indeterminate
tags:
  - CSS
  - Diseño
  - Pseudo-clase
  - Referencia
  - Web
translation_of: Web/CSS/:indeterminate
---
{{CSSRef}}

La [pseudo-clase](/es/docs/Web/CSS/Pseudo-classes) **`:indeterminate`** de [CSS](/es/docs/Web/CSS) representa cualquier elemento de formulario cuyo estado sea indeterminado.

```css
/* Selecciona cualquier <input> cuyo estado sea indeterminado */
input:indeterminate {
  background: lime;
}
```

Los elementos seleccionados por este selector son:

- Elementos [`<input type="checkbox">`](/es/docs/Web/HTML/Element/input/checkbox) cuya propiedad `indeterminate` se establece en `true` por [JavaScript](/es/docs/Web/JavaScript)
- Elementos [`<input type="radio">`](/es/docs/Web/HTML/Element/input/radio), cuando todos los radio buttons con el mismo valor `name` en el formulario no están marcados
- Elementos {{HTMLElement("progress")}} en un estado indeterminado

## Sintaxis

{{csssyntax}}

## Ejemplos

### Checkbox y radio button

Este ejemplo aplica estilos especiales a las etiquetas asociadas con campos de formulario indeterminados.

#### HTML

```html
<div>
  <input type="checkbox" id="checkbox">
  <label for="checkbox">Esta etiqueta comienza con el color lima.</label>
</div>
<div>
  <input type="radio" id="radio">
  <label for="radio">Esta etiqueta comienza con el color lima.</label>
</div>
```

#### CSS

```css
input:indeterminate + label {
  background: lime;
}
```

#### JavaScript

```js
var inputs = document.getElementsByTagName("input");

for (var i = 0; i < inputs.length; i++) {
  inputs[i].indeterminate = true;
}
```

### Resultado

{{EmbedLiveSample('Checkbox_y_radio_button', 'auto', 50)}}

### Barra de progreso

#### HTML

```html
<progress>
```

#### CSS

```css
progress {
  margin: 4px;
}

progress:indeterminate {
  opacity: 0.5;
  background-color: lightgray;
  box-shadow: 0 0 2px 1px red;
}
```

### Resultado

{{EmbedLiveSample('Barra_de_progreso', 'auto', 30)}}

## Especificaciones

| Especificación                                                                                   | Estado                               | Comentarios                                                   |
| ------------------------------------------------------------------------------------------------ | ------------------------------------ | ------------------------------------------------------------- |
| {{SpecName('HTML WHATWG', '#selector-indeterminate', ':indeterminate')}} | {{Spec2('HTML WHATWG')}}     | Ningún cambio.                                                |
| {{SpecName('HTML5 W3C', '#selector-indeterminate', ':indeterminate')}}     | {{Spec2('HTML5 W3C')}}         | Define la semántica de HTML y la validación de restricciones. |
| {{SpecName('CSS4 Selectors', '#indeterminate', ':indeterminate')}}         | {{Spec2('CSS4 Selectors')}} | Ningún cambio.                                                |
| {{SpecName('CSS3 Basic UI', '#indeterminate', ':indeterminate')}}         | {{Spec2('CSS3 Basic UI')}} | Define la pseudo-clase, pero no la semántica asociada.        |

## Compatibilidad con navegadores

{{Compat("css.selectors.indeterminate")}}
