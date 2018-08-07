---
layout: post #
title: 48 Gestor de sessions # Generat automàticament
date: 2018-08-07 # Data
description:  # Argument
keywords:  # Paraules clau
coments:  # Comentaris
---

Quan instal·lem un nou escriptori `sudo apt install ubuntu-budgie-desktop` potser, es canvien els components de lan pantalla de login i els gràfics que indiquen que el sistema va arrancant.

Per elegir o configurar de nou aquesta pantalla d'inici de sessió hem de configurar el **gestor de sessions**, així doncs, imaginem que treballem amb **Gnome 3**, però hem instal·lat d'escriptori **Budgie**, ens l'instal·lació ens preguntarà pel gestor de sessions que volem mantenir. Si més avant vullguerem canviar-lo ho fariem així:

```
sudo dpkg-reconfigure lightdm
```

D'aquesta manera canviariem del gestor de sessions `gdm` que ve amb **Gnome 3** al gestor de sessions `lightdm` que instal·la Budgie, d'aquesta manera tot és més lleuger.


Exemple:

![gdm i lightdm](https://4.bp.blogspot.com/-qVJK46ksFB4/Ud6U3rVjfCI/AAAAAAAAAbg/UojPGDNH76E/s1600/logsk.jpg)

Exemple de pantalla on es veu com s'elegeix el gestor de sessions:

![Terminal](https://2.bp.blogspot.com/-q6H85Yf0xTM/Ud6VbC9jxCI/AAAAAAAAAbo/SH4KQu3IvJ8/s1600/lightdm2.png)
