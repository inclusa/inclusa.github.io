---
layout: post #
title: 43 Suspendre - Hivernar # Generat automàticament
date: 2018-04-07 # Data
description:  # Argument
keywords:  # Paraules clau
coments:  # Comentaris
---

Els diversos procediments per gestionar un equip GNU/Linux en quan a encentre i apagar serien els següents

**Suspendre el sistema**: `systemctl suspend`. Es mantenen els procesos en RAM, quan s'alça el sistema tot corre com abans. Cal tenir en compte que no s'ha de tallar el corrent elèctric.

**Hivernar el sistema**: `systemctl hivernate`. Es crea una còpia imatge al disc dur. Quan tornem a alçar el sistema volca aquesta còpia en RAM reprenent els processos hivernats.

**Apagar el sistema inmediatament**: `poweroff`

**Apagar el sistema ràpidament**: `halt`

**Apagar el sistema immediatament**: `shutdown -h now`

**Apagar el sistema en 5 minuts**: `shutdown -h +5`

**Apagar el sistema a les 23:45 h**: `shutdown -h 23:55`

**Reiniciar el sistema immediatament**: `reboot`

**Reiniciar el sistema immediatament**: `shutdown -r now`

**Reiniciar el sistema en 5 minuts**: `shutdown -r +5`

**Cancel·lar ordre shutdown**: `shutdown -c`
