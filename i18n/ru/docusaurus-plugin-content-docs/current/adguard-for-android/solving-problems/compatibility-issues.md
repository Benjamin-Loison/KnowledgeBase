---
title: Известные проблемы совместимости с приложениями для Android
sidebar_position: 14
---

:::info

В этой статье рассказывается об AdGuard для Android — многофункциональном блокировщике рекламы, который защищает ваше устройство на системном уровне. Чтобы увидеть, как он работает, [скачайте приложение AdGuard](https://agrd.io/download-kb-adblock)

:::

## VPN-приложения

Если вы используете AdGuard в режиме маршрутизиции *Локальный VPN*, вы не можете одновременно запускать другие VPN-приложения. Чтобы решить проблему, предлагаем:

- Использовать [AdGuard VPN](https://adguard-vpn.com/welcome.html): в *Режиме интеграции* два приложения могут работать одновременно
- Использовать ваш VPN в качестве [исходящего прокси-сервера](../solving-problems/outbound-proxy.md) и прописать его параметры в AdGuard
- Выбрать режим *Автоматический прокси*. AdGuard больше не будет использовать локальный VPN и вместо этого перенастроит iptables
- Выбрать режим *Ручной прокси*. Для этого перейдите в раздел *Настройки* → *Фильтрация* → *Сеть* → *Режим маршрутизации*

:::note Совместимость

*Автоматический прокси* доступен только на рутованных устройствах. Для *Ручного прокси* root-доступ требуется на устройствах с Android 10 или выше.

:::

## Частный DNS

Функция Частного DNS была представлена в Android Pie. До версии Q Частный DNS не нарушал логику фильтрации AdGuard DNS, и переадресация DNS через AdGuard работала нормально. Начиная с версии Q наличие Частного DNS вынуждает приложения перенаправлять трафик через системный резолвер вместо AdGuard. Более подробную информацию можно найти [в блоге разработчиков Android](https://android-developers.googleblog.com/2018/04/dns-over-tls-support-in-android-p.html).

- Чтобы решить проблему с Частным DNS, используйте правило `$network`

Некоторые производители устройств скрывают настройки Частного DNS и по умолчанию устанавливают Автоматический режим. Таким образом, отключить Частный DNS невозможно, но можно заставить систему думать, что сервер недействителен. Его можно заблокировать с помощью правила `$network`. Например, если система по умолчанию использует DNS-сервер от Google, можно добавить правила `|8.8.4.4^$network` и `|8.8.8.8^$network`, чтобы его заблокировать.

## Неподдерживаемые браузеры

### UC браузеры: UC Browser, UC Browser для x86, UC Mini, UC Browser HD

Чтобы фильтровать HTTPS-трафик, AdGuard добавляет свой сертификат в пользовательское хранилище. Браузеры UC не доверяют пользовательским сертификатам, поэтому AdGuard не может фильтровать их HTTPS-трафик.

- Чтобы решить эту проблему, переместите сертификат [в системное хранилище сертификатов](../solving-problems/https-certificate-for-rooted.md/)

:::note Совместимость

Требуется root-доступ.

:::

### Браузер Dolphin: Браузер Dolphin, Экспресс-браузер Dolphin

AdGuard не может фильтровать его трафик при работе в режиме *Ручной прокси*, потому что этот браузер игнорирует системные настройки прокси.

- Используйте режим *Локальный VPN* для решения этой проблемы

### Opera mini: Opera mini, Opera mini с Яндексом

Opera mini по умолчанию пропускает трафик через сжимающий прокси-сервер, а AdGuard не может распаковывать и фильтровать трафик одновременно.

- На данный момент решения нет

### Браузер Puffin: Браузер Puffin, Браузер Puffin Pro

Браузер Puffin по умолчанию пропускает трафик через сжимающий прокси-сервер, а AdGuard не может распаковывать и фильтровать трафик одновременно.

- На данный момент решения нет
