---
layout: post # 
title: 64 Actualitzant Docker Portainer # Generat automàticament
date: 2020-08-31 # Data
description:  # Argument
keywords:  # Paraules clau
coments:  # Comentaris
toc: true
---

Portainer és un gestor de Docker que facilita molt el manteniment dels contenidos.

Primer parem el contenidor

```bash
docker stop portainer
```

Esborrem el contenidor

```bash
docker rm portainer
```

Actualitzem la imatge a l'última versió

```bash
docker pull portainer/portainer:latest
```

Escrivim el comandament per deplegar el servei

```bash
docker run -d -p 9000:9000 --name portainer --restart always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer
```

Fonamentat en aquest lloc: [NeoSiteLinux](https://www.neositelinux.com/actualizando-contenedor-docker)
 
