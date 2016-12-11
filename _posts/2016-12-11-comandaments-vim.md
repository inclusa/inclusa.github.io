---
layout: post
title: 18 Funcions en Vim
date:  2016-12-11 00:00:00
description: Assignació de funcions a tecles
---

A vim es ponden assignar tecles per a funcions.

Es tracta d'atorgar funcions per tal de no estar escrivint sempre el mateix.

La diferència amb un `snippe` és que les `funcions` introdueixen un nombre variable, com ara la data.

Assignarem la funció de *data* i *hora* a la tecla `<F5>`.

En un primer pas podem exercutar de forma independen, sense assignar la tecla des del mode de comandaments de Vim:

```
:put =strftime(\"%c\")
```

També es pot fer així:

```
:put =strftime('%c')
```

O simplement així:

```
:pu=strftime('%c')
```

Ara assignarem la tecla `<F5>` per tal d'introduir la data i l'hora pulsant aquesta tecla:


```
:nnoremap <F5> "=strftime("%c")<CR>P
```

Eixida:

```
dg 11 des 2016 09:49:21 CET
```

Es poden utilizar aquest codi segons la necessitat:

```
Format String              Example output
-------------              --------------
%c                         Thu 27 Sep 2007 07:37:42 AM EDT (depends on locale)
%a %d %b %Y                Thu 27 Sep 2007
%b %d, %Y                  Sep 27, 2007
%d/%m/%y %H:%M:%S          27/09/07 07:36:32
%H:%M:%S                   07:36:44
%T                         07:38:09
%m/%d/%y                   09/27/07
%y%m%d                     070927
%x %X (%Z)                 09/27/2007 08:00:59 AM (EDT)
%Y-%m-%d                   2016-11-23
%F                         2016-11-23 (works on some systems)

RFC822 format:
%a, %d %b %Y %H:%M:%S %z   Wed, 29 Aug 2007 02:37:15 -0400

ISO8601/W3C format (http://www.w3.org/TR/NOTE-datetime):
%FT%T%z                    2007-08-29T02:37:13-0400

```

Font: [http://vim.wikia.com/wiki/Insert_current_date_or_time](http://vim.wikia.com/wiki/Insert_current_date_or_time)
