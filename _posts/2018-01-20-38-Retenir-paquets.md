---
layout: post #
title: 38 Retenir paquets # Generat automàticament
date: 2018-01-20 # Data
description:  Retenir paquets en distros derivades de Debian # Argument
keywords: dpkg retenir  # Paraules clau
coments: Utilitat per bloquejar les actualitzacions de paquets concrets # Comentaris
---

Amb la utilitat `dpkg` podem **bloquejar** o **retenir** paquets que ens interessa, per alguna raó, mantenir una versió concreta dels mateixos.

Així amb l'extensió `dpkg get-selections` podem visualitzar i canviar l'estat dels mateixos.

1. Mirar l'estat dels paquets: `dpkg --get-selections`.
2. Filtrar directament el paquet que ens interessa: `dpkg --get-selections firefox`
3. Evitar que s'actualitze el paquet, en aquest cas **Firefox**: `dpkg --get-selections firefox`. La qual cosa el marcarà com a `hold`, així, `firefox hold`.
4. Si fem una actualització pdrem veure que el sistema ens indica que no s'actualitzarà, amb aquest missatge: `The following packages have been kept back: firefox firefox-globalmenu`.
5. Per tornar a permetre la seua instal·lació: `echo "firefox install" | sudo dpkg --set-selections`.

Exemple:

Llistem paquets: `dpkg --get-selections`


    xournal                     hold
    xpra                        install
    xrdp                        install
    xsane                       install
    xsane-common                install
    xscreensaver                deinstall
    xscreensaver-data           deinstall
    xsel                        install

Font: [Taringa](https://www.taringa.net/posts/linux/16014894/Bloquear-la-actualizacion-de-paquetes-en-Debian-y-Ubuntu.html)
