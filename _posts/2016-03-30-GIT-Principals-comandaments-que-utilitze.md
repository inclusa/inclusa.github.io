---
layout: post
title: 03 GIT - Princials comandaments
date: 2016-03-30 00:00:00
description: Descripció de comandaments de GIT
---

# 1. Iniciar un repositori git

```
$ git init
```

# 2. Configurar-lo

```
$ git config --global user.name "John Doe"
```

```
$ git config --global user.email johndoe@example.com
```

# 3. Afegir arxius de rastreig

Cada vegada que modifiquem alguna cosa cal dir-li a GIT que ho tinga en compte.

```
$ git add .
```

# 4. Crear branca

```
$ git checkout -b gh-pages
```


# 5. Canviar de branca

```
$ git checkout master
```


# 6. Mirar en quina branca estem

```
$ git branch
```

# 7. Desfer últim commit

```
$ git reset --hard HEAD~1
```

# 8. Desfer fins arribar a 5 commits abans

```
$ git reset --hard HEAD~5
```

# 9. Desfer el que tenim al GIT local i baixar el que hi ha al server

```
$ git fetch
```

# 10. Clonar repositori remot

```
$ git clone https://github.com/inclusa/inclusa
```

# 11. Sincronitzar des del repositori remot al local

```
$ git pull
```

# 12. Sincronitzar des del repositori local al remot

```
$ git push
```

# 13. Evitar que GIT demane usuari i contrasenya

```
$ git config --global credential.helper. store
```

La contrasenya del repositori remot queda magatzemada al fitxer `.git-credentials`

# 14. No guardar la contrasenya en disc

```
$ git config --global credential.helper 'cache --timeout=3600'
```

Transcorreguda un hora tornarà a demanar la contrasenya.


