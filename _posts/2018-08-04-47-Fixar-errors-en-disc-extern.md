---
layout: post #
title: 47 Fixar errors en disc extern # Generat automàticament
date: 2018-08-04 # Data
description: Fixar errades de disc # Argument
keywords:  # Paraules clau
coments:  # Comentaris
---

M'he trobat en la circumstància de connectar un disc dur extern que no podia arrancar.

Mitjançant `gparted` he pogut observar que tenia un format `NTFS`, en utilitzar GNU/Linux necessitarem aquestes utilitats per tal de gestionar aquest format:

```
$ sudo apt install ntfs-3g ntfsprogs
```

Per tal de fixar les errades en el disc amb format `NTFS` caldrà serguir aquesta lògica:

```
sudo ntfsfix /dev/partitionName
```

Així que l'apliquem:

```
sudo ntfsfix /dev/sdd1
```

L'errada podria haver estat causada perquè el portàtil que estava sincronitzant el backup s'havera quedat sense energia.

En cas de trobar-nos amb errades en un pendrive:

1. Obririem un terminal i mirem les unitats muntades:

```
$ df -h
```
2. Desmuntem la unita

```
$ sudo umount /dev/sdd1
```

3. Reparem els permisos de la unitat

```
$ sudo fsck -r /dev/sdd1
```

Font:
- [William Markito](https://wmarkito.wordpress.com/2010/12/29/how-to-fix-mftmirr-does-not-match-mft-record-0/)
- [Inclusa](http://inclusa.blogspot.com/2015/02/reparant-permisos-corruptes-al-pendrive.html)
