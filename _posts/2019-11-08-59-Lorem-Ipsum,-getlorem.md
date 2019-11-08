---
layout: post #
title: 59 Lorem Ipsum, getlorem # Generat automàticament
date: 2019-11-08 # Data
description:  # Argument
keywords:  # Paraules clau
coments:  # Comentaris
---

Lorem Ipsum és un text habitualment utilitzat en disseny gràfic i en demostracions tipogràfiques. Es tracta d'un text derivat d'un obra de Ciceró.

Per tal de generar el text i provar la formatació del mateix en diferents contextos hem arribat a aquest recurs [getlorem](https://getlorem.com/), el qual deixa generar en la mateixa web el bloc de text en diverses modalitats.

Però també es pot instal·lar a l'ordinador per mig de `npm`, així:

```bash
sudo npm -g install getlorem
```

Després el podrem cridar des de la terminal indicant els paràmetres conveients:

```bash
getlorem --units words --count 50
```

Així obtindriem:

```bash
Donec suscipit aliquet class tellus, pellentesque volutpat quisque.
```

Podem canviar els parametres `words`, `paragraphs`, `bites` o `lists`.

