---
layout: post # page | post
title: 35 Linux en un pendrive
date: 2017-09-09 
description: Copiar una distro Linux a un pendrive    # Argument
keywords: distro linux pendrive                       # Paraules clau
coments: true    # Comentaris activats
---

Per tal de grabar una distro Linux en un pendrive caldra seguir aquests passos:

1. Saber com s'anomena el dispositiu USB (pendrive) on volem instal·lar la distro.
2. Escriure el comandament pertinent

Per esbrinar com s'anomena el pendrive al sistema:

```bash
lsblk
```

Aquest comandament es retonarà un llistat, caldrà esbrinar quin és el dispositiu, en aquest cas:

```bash
sdb
```

Llavors indiquem que es copie la distro al pendrive:

```bash
sudo dd if=lliurex-escriptori_64bits_16_20170731.iso of=/dev/sdb bs=4M
```

ESPEREM TOT EL QUE CALGA, costa un poquet.

Quan el procés acabe ja podrem arrancar des del pendrive.
