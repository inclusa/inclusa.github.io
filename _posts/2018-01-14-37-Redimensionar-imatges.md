---
layout: post # Sustituye el layout si lo usas uno diferente
title: 37 Redimensionar imatges # Nombre generado automáticamente
date: 2018-01-14 00:00:00 # Data
description:  Redimensionar imatges amb Image Magic # Argument
keywords: imatges # Paraules clau
coments: Redimensionar imatges des del terminal  # Comentaris
---

Podem redimensionar les imatges des del terminal seguit aquest patró:

```
convert imatge.jpg -resize 700 -quality 50 imatge_nova.jpg
```

La tecnologia que hi ha per baix és Image Magic. Adaptant els paràmetres a les necessitats es poden obtenir les dimensions pertinents.

També podem diverses imatges a un sol fitxer **PDF**.

```
convert imatge01.jpg imatge02.jpg comipacio.pdf
```

