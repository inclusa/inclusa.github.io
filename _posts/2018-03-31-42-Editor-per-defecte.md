---
layout: post #
title: 42 Editor per defecte # Generat automàticament
date: 2018-03-31 # Data
description: Configurar Vim com editor per defecte al sistema # Argument
keywords:  # Paraules clau
coments:  # Comentaris
---

Per tal d'editar sempre amb l'editor que predeterminem al nostre sistema caldrà executar aquesta ordre:

```bash
sudo update-alternatives --config editor
```

La qual ens tornarà aquest text:


```bash
Hi ha 4 possibilitats per a l'alternativa editor (que proveeix /usr/bin/editor).

  Selecció    Camí               Prioritat  Estat
------------------------------------------------------------
  0            /bin/nano            40        mode automàtic
  1            /bin/ed             -100       mode manual
  2            /bin/nano            40        mode manual
* 3            /usr/bin/vim.basic   30        mode manual
  4            /usr/bin/vim.tiny    15        mode manual

Premeu retorn per a mantenir l'opció per defecte[*], o introduïu un número de selecció: 
```

Caldrà introduir el nombre de l'editor que desitgem.

Ara sempre que editem un text en terminal ho farem en el nostre editor predeterminat.
