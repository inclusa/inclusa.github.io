---
layout: post
title: 52 Formigues
date:  2017-03-19 00:00:00
---


En el món natural, les formigues, inicialment, vaguen de form aleatòria. Quan troben el menjar tornen a la seua colonia deixan un rastre de feromones.

Si altres formigues troben aquest rastre, es probable que éstes no seguisquen el camí aleatòriament, potser que seguisquen el rastre de feromonas, reforçant-lo, si troben menjar finalment.

Amb el pas del temps, el rastre de feromones comença a evaporar-se, reduïnt-se així la seua força d'atracció.

A l'evaporar-se, les feromones, determinen un temps limitat a la solució.

El fluxe de formigues i la quantitat determinarà el camí més curt, optimitzant l'energia alliberada per a la recol·leció de l'aliment.

Aquest fenòmen, anomenat *estigmergia*, s'utilitza en societats animals.

És un sistema de resolució de problemes *autoorgnaitzat*, basat en la *retroalimentació positiva* (feromones) i la *retroalimentació negativa* (evaporació).

L'algoritme implica que cada formiga, de manera incremental, constituix una solució del problema.

Fases:

1. Construcció de la ruta
2. Evaluació de la millor ruta
3. Modificació de la ruta

### Algoritme

```bash
  procedure ACO_MetaHeuristic
    while(not_termination)
       generateSolutions()
       daemonActions()
       pheromoneUpdate()
    end while
  end procedure
```

[Wikipedia](https://es.wikipedia.org/wiki/Algoritmo_de_la_colonia_de_hormigas)


### L'organització colonial

1. Les formigues teixedores són *fundades* per una o varies reines.

2. Lees formigues s'alimenten de larves fins que es desenvolupen en *obreres madures*.

3. Les obreres *ajuden* a criar les noves nidades posades per la reina.

4. Amb l'augment dels individus, augmenta la *productivitat*.

5. Les oreres realitzen *tasques esencials* per a la superfivència de la colonia: recol·lecten, la construeixen i la defenen.

6. La creació d'una colònia social complexa i organitzada és el resultat de múltiples interaccions *no aleatòries* entre individus, que segueixen *regles simples*.

7. L'*intercanvi d'informació* i *modulació del comportament* de les obreres, que ocòrren durant les interaccions obrera-obrera són facilitats per l'ús de *senyals de comunicació* químiques i tàctils.

8. Les recol·lectores que han tingut èxit en la seua cerca deixen rastres que *ajuden a altres* obreres a localitzar noves fonts d'aliments.

9. Els rastres s'utilitzen per les *patrulleres* per reclutar obreres contra intrussos en els seus territoris.

10. La *comunicació multimodal*, químia i tàctil, contribueix, de forma significativa a la *autoorganització* de la colònia.

11. *Comportament social de transport*: una obrera portarà altra en les seues mandíbules fins el lloc on requerisca atenció.

12. Les formigues del gènere Oecophylla són conegudes pel notable *comportament cooperatiu* que utilitzen en la construcció de les seues colònies.

[Wikipedia](https://es.wikipedia.org/wiki/Oecophylla#Desarrollo_de_la_colonia_y_organizaci.C3.B3n_social)
