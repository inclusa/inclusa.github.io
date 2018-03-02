---
layout: post #
title: 41 Màquines Virtuals # Generat automàticament
date: 2018-02-24 # Data
description: Arranc i configuració de màquines virtuals des del terminal  # Argument
keywords: virtualbox # Paraules clau
coments: Gestió de les màquines virtuals amb VirtualBox des del terminal  # Comentaris
---

VirtualBox

Per alçar VirtualBox des del terminal primer cal veure la llista de màquines que tenim instal·lades. Tiguem aquestes opcions:

```bash
VBoxManage list [--long|-l] vms|runningvms|ostypes|hostdvds|hostfloppies|intnets|bridgedifs|hostonlyifs|natnets|dhcpservers|hostinfo|hostcpuids|hddbackends|hdds|dvds|floppies|usbhost|usbfilters|systemproperties|extpacks|groups|webcams|screenshotformats
```
Ara sí, mirem les màquines que tenim instal·lades:

### 1. Llistar les màquines virtuals

```bash
VBoxManage list vms
"LliureXServer16" {00000000-0000-0000-0000-000000000000}
```

Ens donarà tant el seu nom com l'uid.

### 2. Iniciar la màquina virtual

Iniciem la màquina virtual així:

```bash
VBoxManage startvm "LliureXServer16"
```

o així:

```bash
VBoxManage startvm 00000000-0000-0000-0000-000000000000
```

Si volem iniciar la màquina de forma remota, `ssh`, sense executar-la des d'una sessió gràfica:

```bash
VBoxSDL --startvm VBoxManage startvm "LliureXServer16"
```

### 3. Pausar la màquina virtual

```bash
VBoxManage controlvm "LliureXServer16" pause
```

### 4. Reiniciar una màquina virtual pausada

```bash
VBoxManage controlvm "LliureXServer16" resume
```

### 5. Resetejar una màquina virtual

```bash
VBoxManage controlvm "LliureXServer16" reset
```

### 6. Apagar la màquina virtual

```bash
VBoxManage controlvm "LliureXServer16" poweroff
```

No utilitzar aquest procediment perquè mata la màquina de colp i podria corrompres.

### 7. Detenir la màquina virtual salvant l'estat actual

```bash
VBoxManage controlvm "LliureXServer16" savestate
```

### 8. Crear una màquina virtual amb les opcions per defecte

```bash
VBoxManage createvm -name "Debian8"
```

### 9. Canviar requeriments de la nostra màquina virtual

```bash
VBoxManage modifyvm "LliureXServer16" -memory "1024MB"
```

### 10. Fonts

- [Paràmetres - VitualBox Manual](https://www.virtualbox.org/manual/ch08.html#vboxmanage-modifyvm)
- Aquest article està basat en l'article de [Guillermo Garron](https://www.virtualbox.org/manual/ch08.html#vboxmanage-modifyvm)`
