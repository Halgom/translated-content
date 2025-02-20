---
title: Geolocation
slug: Web/API/Geolocation
tags:
  - API
  - Advanced
  - Geolocation API
  - Interface
  - Reference
  - Secure context
translation_of: Web/API/Geolocation
---
{{APIRef}}

Интерфейс **`Geolocation`** представляет возможность программно получит местоположение устройства. Он даёт доступ веб-содержимому к позиции пользователя. Это также помогает сайтам и приложениям предоставлять результаты, основываясь полученных данных.

Объект с этим интерфейсом получается с помощью свойства {{domxref("NavigatorGeolocation.geolocation")}} и реализуется объектом {{domxref("Navigator")}}.

> **Примечание:** По некоторым причинам, связанным с безопасностью, когда веб-страница пытается получить доступ к местоположению, пользователь будет уведомлен, а также будет запрошено разрешение. Имейте в виду, что у каждого браузера есть свои политики и методы для запроса этого разрешения.

## Свойства

_Интерфейс `Geolocation` ни реализует, ни наследует никаких свойств._

## Методы

**Интерфейс `Geolocation` не наследует никаких методов**.

- {{domxref("Geolocation.getCurrentPosition()")}} {{securecontext_inline}}
  - : Определяет местоположение устройства и возвращает объект {{domxref("Position")}} с данными.
- {{domxref("Geolocation.watchPosition()")}} {{securecontext_inline}}
  - : Возвращает `long` значение, предоставляет вновь созданную колбэк-функцию, вызываемую при изменении местоположения устройства.
- {{domxref("Geolocation.clearWatch()")}} {{securecontext_inline}}
  - : Удаляет обработчик, созданный с помощью `watchPosition()`.

## Спецификации

{{Specifications}}

## Совместимость с браузерами

{{Compat}}

## Смотрите также

- [Использование геолокации](/ru/docs/WebAPI/Geolocaion/Using_geolocation)
