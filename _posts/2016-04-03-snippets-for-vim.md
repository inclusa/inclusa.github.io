---
layout: post
title: 04 Snippets for Vim
date: 2016-04-03 00:00:00
description: Automatització de text, insertar automàtica contextualitzada
---

[Vim](http://www.vim.org/) processador de textos minimalista, present en molts contextos, admet plugins tan útils com ara els **snippets**.

Els [snippets] no és més con mòduls de codi definit per tal d'escriure's quan es crida. Es tracta de codi que escrivim prèviament i que cridem mitjançat una paraula clau i el tabulador.

Així podem definir **snippets** per cada llenguatge, de forma que segons l'extensió de cada arxiu tindrem disponibles uns **snippets** o altres.

Per tal de tenir presents alguns podem seguir les instruccions que incorporen snippets pel framework [bootstrap].

Passos per tindre-ho disponible:

1. Clonar el repositori de GITHub.
2. Copiar la carpeta **snippets** a **.vim/snippets**

Per utiltizar-los cal posar l'extensió correcta al document que editem i escriure el `nom del snippet + TAB`.



[snippets]:	https://en.wikipedia.org/wiki/Snippet_%28programming%29
[bootstrap]:	https://github.com/bonsaiben/bootstrap-snippets
