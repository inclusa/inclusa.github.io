---
layout: post # 
title: 76 Imprimir des de terminal # Generat automàticament
date: 2023-01-03 # Data
description:  # Argument
keywords:  # Paraules clau
coments:  # Comentaris
---

Imprimim des de terminal tenint en compte que utilitzem CUPS.

`lp fitxer.pdf` Imprimeix l'arxiu en la impressora per defecte.

`lpstat -p -d` Mostra les impressores disponibles.

`lp -d Brother_HL_2250DN_series` Envia l'arxiu a una impressora específica.

`lpoptions -d Brother_HL_2250_series` Defineix per defecte aquesta impressora.

`lp -o landscape -o media=A4 -n 3 arxiu.pdf` S'imprimiran 3 còpies en format horitzontal.

`cancel ID-arxiu` Cancel·la el treball.

`lpmove ID-arxiu Brother_HL_2250_series` Mou el treball a la imprissora indicada.

`cupsenable Brother_HL_2250_series` Habilita aquesta impressora.

`cupsdisable Brother_HL_2250_series` Deshabilita aquesta impressora.


`lp -o landscape -o media=A4 -n 3 *.pdf` Imprimeix 3 vegades, de forma apaisada tots els documents en pdf del directori.

