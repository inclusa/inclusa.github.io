---
layout: post # Sustituye el layout si lo usas uno diferente
title: 89 Generar Claus ssh # Nombre generado automáticamente
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/33dEcCKGBO4?si=CzMjbO13HwylMJmO" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


<iframe width="560" height="315" src="https://www.youtube.com/embed/v2ii8kdXCic?si=jqnFmFzJ0Mx9PeXT" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


Configuració ssh.

Podem configurar diverses claus cap a servidors diferents:

```bash
Host lliurex
    Hostname 172.24.25.100.254

Host Fedora
    Hostmame fedora.domini.es
    User admin

Host Ubuntu
    Hostmanem ubuntu.domini.es
    User root
    Port 2201
```

Despres sols caldrà anomenar el `host` per connectar-se.

Per connectar-se a Lliurex:

```bash
ssh lliurex
```

Per connectar-se a Fedora:

```bash
ssh fedora
```

Per connectar-se a Ubuntu:

```bash
ssh ubuntu
```
