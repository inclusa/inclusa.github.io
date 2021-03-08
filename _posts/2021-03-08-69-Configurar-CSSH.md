---
layout: post # Sustituye el layout si lo usas uno diferente
title: 69 Configurar CSSH # Nombre generado automáticamente
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/3S3_hsqpYg4" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Per tal de crear la configuració per defecte cal escriure:

```bash
cssh
```
Això ens crearà un arxiu de configuració per defecte, l'arxiu `config`:

```bash
.clusterssh
└── config
```

Caldrà crear a mà els arxius `clusters` i `tags`:

```bash
.clusterssh
├── clusters
├── config
└── tags
```

El fitxers `clusters` contindrà el nom de cada grup de servidors:

```bash
# Grup Groc
groc 10.0.2.10 10.0.2.11 10.0.2.12

# Grup Blau
blau 10.0.2.20 10.0.2.21 10.0.2.22

# Grup Verd
verd 10.0.2.30 10.0.2.31 10.0.2.32
```

Així per tal de connectar-nos als servidors del grup groc escriurem:

```bash
cssh -l usuari groc
```

Si ens volem connectar als tres servidors escriurem:

```bash
cssh -l usuari groc blau verd
```

No descriurem el que es pot fer al fitxer tags, al vídeo es pot veure la seua funcionalitat.
