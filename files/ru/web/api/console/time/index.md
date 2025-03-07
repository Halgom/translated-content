---
title: Console.time()
slug: Web/API/Console/time
tags:
  - API
  - DOM
  - Method
  - Reference
  - console
translation_of: Web/API/Console/time
---
{{APIRef("Console API")}}

Запускает таймер, который вы можете использовать для определения, сколько времени занимает выполнение той или иной операции. Вы должны назначить каждому таймеру уникальное имя и таким образом можете запустить до 10000 таймеров на одной странице. Когда вы вызовете {{ domxref("console.timeEnd()") }} с именем, которое использовалось при запуске таймера, браузер отобразит в консоли время (в миллисекундах), прошедшее с момента запуска таймера.

Примеры и более детальная информация находятся в разделе [Таймеры](/ru/docs/DOM/console#Timers "DOM/console#Timers") документации к {{ domxref("console") }}

{{AvailableInWorkers}}

## Синтаксис

```
console.time(label);
```

## Параметры

- `label`
  - : Название нового таймера. Оно однозначно идентифицирует таймер. Используйте то же самое название таймера, когда вызываете {{ domxref("console.timeEnd()") }} для остановки и отображения времени выполнения таймера.

## Документация

| Specification                                                            | Status                           | Comment                    |
| ------------------------------------------------------------------------ | -------------------------------- | -------------------------- |
| {{SpecName("Console API", "#time", "console.time()")}} | {{Spec2("Console API")}} | Первоначальное определение |

## Совместимость с браузерами

{{Compat}}

## Смотрите также

- {{ domxref("Console.timeEnd()") }}
- {{ domxref("Console.timeLog()") }}
- [Opera Dragonfly documentation: Console](http://www.opera.com/dragonfly/documentation/console/)
