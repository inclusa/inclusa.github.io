---
layout: post # Sustituye el layout si lo usas uno diferente
title: 67 Backup script # Nombre generado automáticamente
---

Manera senzilla de fer un backup

```bash
#!/bin/bash
BACK=backup_$(date +%Y%m%d).tar.gz
cd /home/usuari/backup/directori_destí          # Destí backup
tar -czf $BACK /home/usuari/Documents/treball   # Executa el backup
```


### Arxius .tar

Empaquetar

```bash
tar -cvf paquete.tar /dir/a/comprimir/
```

Desempaquetar

```bash
tar -xvf paquete.tar
```

### Arxius .zx

Instal·lar xz

```bash
$ sudo apt install xz-utils
```

Comprimir

```bash
xz foo
```

Descomprimir

```bash
xz -v -d archives.tar.xz
```

Empaquetar i comprimir

```bash
tar -cJf foo.tar.xz foo
```

Desempaquetar i descomprimir

```bash
tar -xf foo.tar.xz
```

Per saber-ne més

    nixCraft

Flayers

-x : Extract/get/unzip files from an archive.

-f archive.tar.xz : Use this archive file or device archive for extracting files

-J OR –xz : Filter the archive through xz command. Hence, we install xz using package manager.

-v : Verbose. Show progress.

-t : List file stored inside .tar.xz/.xz archive.

### Arxius .gz

Comprimir

```bash
gzip -9 index.php
```

Descomprimir

```bash
gzip -d index.php.gz
```

### Arxius .tar.gz

Comprimir

```bash
tar -czvf empaquetado.tar.gz /carpeta/a/empaquetar/
```

Descomprimir

```bash
tar -xzvf archivo.tar.gz
```

### Arxius .rar

Comprimir

```bash
rar directori.rar directori
```

Desomprimir

```bash
unrar directori.rar
```

### Arxius .zip

Comprimir

```bash
zip archivo.zip carpeta
```

Descomprimir

```bash
unzip archivo.zip
```


