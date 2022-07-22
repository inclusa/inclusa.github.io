---
layout: post # Disseny
title: 73 Imatge de disc dd # Generat de forma automàtica
date: 2022-07-22 # Data
description:  # Argument
keywords:  # Paraules clau
coments:  # Comentaris
---

Per tal de copiar una imatge a un pendrive seguirem aquest procediment.

Primer caldrà identificar la unitat del pendrive, això serà crític, ja que una errada en aquest pas podria portar-nos a formatar un disc senser per error.

Per identifiar-ho:

```bash
sudo dmesg | grep -i 'attached' 
```

Això ens donarà la següent informació:

```bash
[sudo] contrasenya per a lliurex: 
[ 2167.098710] sd 3:0:0:0: [sdd] Attached SCSI removable disk
[11682.594403] sd 3:0:0:0: [sdd] Attached SCSI removable disk
```

Identifiquem el pendrive com a [sdd] en aquest cas.

En cas de dubte executar `sudo gparted` i identificar molt clarament la unitat en qüestió.

```bash
dd if=/home/lliurex/Baixades/lliurex.iso of=/dev/sdd bs=16M oflag=direct status=progress

```
