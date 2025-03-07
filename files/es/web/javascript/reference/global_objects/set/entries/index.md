---
title: Set.prototype.entries()
slug: Web/JavaScript/Reference/Global_Objects/Set/entries
translation_of: Web/JavaScript/Reference/Global_Objects/Set/entries
original_slug: Web/JavaScript/Referencia/Objetos_globales/Set/entries
---
{{JSRef}}

El método **`entries()`** devuelve un nuevo objeto de tipo `Iterator` que contiene **un array de tuplas `[value, value]`** por cada elemento en el `Set` original, manteniendo el orden de inserción. En los objetos de tipo `Set` no existe una clave key como ocurre en los objetos de tipo `Map`. Sin embargo, para mantener una API similar a la de los objetos de tipo `Map`, cada _entry_ contiene el mismo valor para su clave y valor, devolviendo por tanto un array de tuplas `[value, value]`.

{{EmbedInteractiveExample("pages/js/set-prototype-entries.html")}}

El código de este ejemplo interactivo esta almacenado en un repositorio de GitHub. Si quieres contribuir al proyecto de ejemplos interativos, simplemente clona <https://github.com/mdn/interactive-examples> y envíanos una pull request.

## Sintaxis

```
mySet.entries()
```

### Valor de retorno

Un nuevo objeto de tipo `Iterator` que contiene un array de tuplas `[value, value]` por cada elemento en el `Set` original, en orden de inserción.

## Ejemplos

### Usando el método `entries`

```js
var mySet = new Set();
mySet.add('foobar');
mySet.add(1);
mySet.add('baz');

var setIter = mySet.entries();

console.log(setIter.next().value); // ["foobar", "foobar"]
console.log(setIter.next().value); // [1, 1]
console.log(setIter.next().value); // ["baz", "baz"]
```

## Especificaciones

| Especificación                                                                                           | Estado                       | Commentario         |
| -------------------------------------------------------------------------------------------------------- | ---------------------------- | ------------------- |
| {{SpecName('ES2015', '#sec-set.prototype.entries', 'Set.prototype.entries')}} | {{Spec2('ES2015')}}     | Definición inicial. |
| {{SpecName('ESDraft', '#sec-set.prototype.entries', 'Set.prototype.entries')}} | {{Spec2('ESDraft')}} |                     |

## Compatibilidad de navegadores

{{Compat("javascript.builtins.Set.entries")}}

## Ver también

- {{jsxref("Set.prototype.keys()")}}
- {{jsxref("Set.prototype.values()")}}
