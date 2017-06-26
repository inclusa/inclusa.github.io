---
layout: post # page | post
title: 30 Compartir arxius amb Python
date: 2017-06-26 
description: Compartir arxius amb alçant un xicotet server amb Python # Argument
keywords: server python  # Paraules clau
coments: true    # Comentaris activats
---

Compartir arxius ja no es sols cosa de *Dropbox* o *Google Drive*, les quals són molt bones solucions. Podem fer-ho de manera senzilla amb Pyhton, així:

1. Creem una carpeta, per exemple, li posem de nom `share`
2. Dins d'aquesta carpeta podem posar arxius
3. Ens situem dins d'aquest directori, el directori que anomenat `share` i llancem aquest comandament `python -m http.server 8090`
4. Obrim el navegador amb l'adreça `localhost:8090`. Si l'obrim des d'un altre ordinador de la xarxa local cal cambiar `localhost`per la `ip` de l'ordinador que conté la carpeta `share`.

Font: [TECHBASICS](https://techpickup.wordpress.com/2017/06/25/how-to-share-files-in-network/)
