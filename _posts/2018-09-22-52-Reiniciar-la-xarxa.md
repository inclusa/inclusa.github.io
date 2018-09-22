---
layout: post #
title: 52 Reiniciar la xarxa # Generat automàticament
date: 2018-09-22 # Data
description:  # Argument
keywords:  # Paraules clau
coments:  # Comentaris
---

Sovint em passa que arranque l'ordinador i oblide que el router està apagat.

A Ubuntu 18.04 la cosa es soluciona, al cap d'un minut, sembla que hi ha un cron que revisa constantment la xarxa.

El procediment de reiniciar la xarxa ha anat canviant al llarg dels anys, supose que el canvi a System D també ha tingut alguna cosa a veure.

El cas és que cal saber com reiniciar la xarxa de forma efectiva. Ací recollim alguns procediments:


1. **netplan** `sudo netplan apply`
2. **systemctl** `sudo systemrestart NetworkManager.service`
3. **service** `sudo service network-manager restart`
4. **nmcli** `sudo nmcli networking off && sudo nmcli networking on`
5. **system V init** `sudo /etc/init.d/networking restart` o `sudo /etc/init.d/network-manager restart`
6. **ifup/ifdown** `sudo ifdown -a && sudo ifup -a`

Font: [linuxconfig.org](https://linuxconfig.org/how-to-restart-network-on-ubuntu-18-04-bionic-beaver-linux)

