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

# 15. Borrar branca i borrar-la del server

Objectiu: volem borrar la branca gh-pages

```
$ git branch -d gh-pages           # elimina branca local

$ git push origin :gh-pages        # elimina branca remota

```

# 16. Iniciar repositori en GITHub des de terminal amb el protocol `https://`

```
echo "# repositori" >> README.md
git init
git add README.md
git commit -m "comentari"
git remote add origin https://github.com/usuari/repositori.git
git push -u origin master
```

# 17. Explicació

`echo`: Afegix la informació al fitxer, si no existeix el crea

`git init`: Inicia el repositori creant els arxius de rastreig a .git

`git add README.md`: Afegig l'arxiu README.md per tal que es rastrege

`git commit -m "comentari"`: Crea el punt d'emmagatzemmament del contigut actual, emmgatzema el contingut de del projecte establint fixant un punt, també afegeix un comentar

`git add remote add origin https://`: Afegeig repositori remot

`git push -u origin master`: publica el repositori local a la branca `master` remota

# 18. Publicar a un repositori existent a GITHub des de la línia de comandamentsamb el protocol `https://`

```
git remote add origin https://github.com/usuari/repositori.git
git push -u origin master
```

# 19. Iniciar repositori en GITHub des de terminal amb el protocol `ssh`

```
echo "# repositori" >> README.md
git init
git add README.md
git commit -m "comentari"
git remote add origin git@github.com:usuari/repositori.git
git push -u origin master
```

# 20. Publicar a un repositori existent a GITHub des de la línia de comandamentsamb el protocol `ssh`

```
git remote add origin git@github.com:usuari/repositori.git
git push -u origin master
```


# 21. Fonts

- [git - la guia sencilla](http://rogerdudler.github.io/git-guide/index.es.html)
- [Become a git guru](https://www.atlassian.com/git/tutorials/)
- [Pro Git](https://git-scm.com/book/es/v1)
- [Cheat Sheets](http://cheat.errtheblog.com/s/git)
- [GIT - Tutorials Point](http://www.tutorialspoint.com/git/)

# 22. GITHub

- [Iniciar repositori](https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/#platform-linux)

