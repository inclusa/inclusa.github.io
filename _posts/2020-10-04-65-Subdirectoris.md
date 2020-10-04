---
layout: post # Sustituye el layout si lo usas uno diferente
title: 65 Subdirectoris # Nombre generado automáticamente
---

Volem crear un directori que continga subdirectoris amb una mateixa acció.


```bash
makedir -p directori/{a,b,c}
```

Resultat

```bash
.
└── directori
    ├── a
    ├── b
    └── c
```


Volem crear un directori que continga subdirectoris amb un prefixe.

```
makedir -p directori/bk_{a,b,c}
```

Resultat

```bash
.
└── directori
    ├── bk_a
    ├── bk_b
    └── bk_c
```
