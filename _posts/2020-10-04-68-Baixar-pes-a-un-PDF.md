---
layout: post # Sustituye el layout si lo usas uno diferente
title: 68 Baixar pes a un PDF # Nombre generado automáticamente
---

```bash
#!/bin/bash

echo "Utilitat per reduir PDF de pes"
echo "Introdueix el nom de l'arxiu amb l'extensió"
read ARXIU

pdf2ps $ARXIU $ARXIU.ps
ps2pdf $ARXIU.ps $ARXIU-red.pdf
```
