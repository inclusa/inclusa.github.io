---
layout: post # Disseny
title: 75 Agrupar PDFs # Generat de forma automàtica
date: 2022-07-25 # Data
description:  # Argument
keywords:  # Paraules clau
coments:  # Comentaris
---

Per tal d'agrupar PDFs en un sol document podem fer-ho amb pdftk.

```bash
pdftk 01.pdf 02.pdf 03.pdf output eixida.pdf
```

```bash
pdftk *.pdf output eixida.pdf
```

