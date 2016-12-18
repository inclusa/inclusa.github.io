---
layout: post
title: 17 Copiar amb recurrència
date:  2016-12-10 00:00:00
description: Copiem un arxiu diverses vegades en una mateixa línia
---

En un primer moment generem 12 arxius buits d'aquesta manera:

```
$ touch {01..12}.md
```
Això ens crearà 12 arxius buits així:

```
01.md  03.md  05.md  07.md  09.md  11.md
02.md  04.md  06.md  08.md  10.md  12.md

```

Per copiar el mateix arxiu de forma recurrent, és a dir, diverses vegades, cal definir la variable `d` i exercutar-la.

```bash
$ for d in 01.md 02.md 03.md 04.md 05.md 06.md 07.md 08.md 09.md 10.md 11.md 12.md; do cp ini.md $d; done

```

D'aquesta manera aconseguim generar 12 arxius iguals, però amb noms diferents.

Font: [IMD](http://www.imd.guru/#menu)
