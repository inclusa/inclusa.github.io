---
layout: post # page | post
title: 36 Comprimir arxius en GNU Linux
date: 2017-09-09 
description: Comprimir amb diferents formats de compressió   # Argument
keywords: tar tgz zip rar       # Paraules clau
coments: true    # Comentaris activats
---

Comprimir - simplificat

# TAR

Comprimir

```bash
tar {opcions} fitxer_comprit.tar fitxer1 fitxer2 directori1/ ...
```

```bash
tar cfv fitxer_comprit.tar arxiu1.txt executable.sh directori/
```

Opccions:

`c`: *compress*, comprimeix.

`f`:  *file*, indica que es crearà un fitxer comprimit.

`v`: *verbose*, mostrarà les carpetes i arxius comprimits.

`vv`:  mostrarà informació adicional de cada arxiu.

Descomprimir

```bash
tar xvf fitxer_comprimit.tar
```

# ZIP

Instal·lar

```bash
sudo apt install zip unzip
```

Comprimir

```bash
zip -r comprimit.zip fitxer1 directori1/ ftxer2
```

Descomprimir

```bash
unzip fitxer.zip
```

# RAR

Instal·lar

```bash
sudo apt install rar
```

Comprimir

```bash
rar a arxiu.rar fitxer1 directori1/ fitxer2
```
`a`: afegir

Descomprimir

```bash
rar x arxiu.rar
```
