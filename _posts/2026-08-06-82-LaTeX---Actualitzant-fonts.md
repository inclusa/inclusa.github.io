---
layout: post # Sustituye el layout si lo usas uno diferente
title: 82 LaTeX   Actualitzant fonts # Nombre generado automáticamente
---

Si no consegueixes baixar el paquet de fonts per a LaTeX `sourcesanpro.sty`. El pots baixar des de `ftp.fu-berlin.de/tex/CTAN/fonts/sourcesanspro.zip`.

Després caldrà que el copies a `/usr/share/texmf/tex/latex`.

Finalment li hauràs de dir al sistema que tinga en compte aquesta font amb aquest comandament:

```latex
updmap-sys --enable Map=SourceSansPro.map.
```
