# TeSettings

## Самописный ~~велосипед~~ парсер .ini файлов для Qt. 

## Почти повторяет интерфейс QSettings, но имеет некоторые отличия в функционале:
- Если название параметра является числом, то он сортируется как число. (QSettings все параметры сортирует как строки).
- Работа с комментариями: чтение и запись комментариев к секциям и параметрам.

## Сборка
1. Открыть QtCreator'ом
2. Собрать в release-режиме (по надобности добавить `#define TE_SETTINGS_QOBJECT` в tesettings.h)
3. Заголовочный файл и файлы библиотеки появятся в ./TeSettings/lib/te_settings/

## Описание работы с классом:
Есть в виде комментариев в заголовочном файле tesettings.h.

## Примеры
Такой конфиг может сформировать QSettings:
```ini
[General]
param1=value1
param2=1

[SECTION_2]
param2_1=value2
param2_2=2

[SECTION_3]
param3_1=value3
param3_2=3
```

А такой - TeSettings:
```ini
[General]
param1=value1 ; Это параметр 1
param2=1 ; Это параметр 2

; Это секция 2
; А это тоже комментарий к секции 2
[SECTION_2]
param2_1=value2
param2_2=2

; Это секция 3
[SECTION_3]
param3_1=value3
; Это
; многострочный
; комментарий
; к параметру param3_2
param3_2=3
```