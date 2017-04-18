---
layout: post
title: 03 GIT - Princials comandaments
date: 2016-03-30 00:00:00
description: Descripció de comandaments de GIT
---

# 1. Iniciar un repositori git

> $ git init

# 2. Configurar-lo

> $ git config --global user.name "John Doe" <br />
> $ git config --global user.email johndoe@example.com

# 3. Afegir arxius de rastreig

Cada vegada que modifiquem alguna cosa cal dir-li a GIT que ho tinga en compte.

> $ git add .

# 4. Crear branca

> $ git checkout -b gh-pages


# 5. Canviar de branca

> $ git checkout master


# 6. Mirar en quina branca estem

> $ git branch

# 7. Desfer últim commit

> $ git reset --hard HEAD~1

# 8. Desfer fins arribar a 5 commits abans

> $ git reset --hard HEAD~5

# 9. Desfer el que tenim al GIT local i baixar el que hi ha al server

> $ git fetch

# 10. Clonar repositori remot

> $ git clone https://github.com/inclusa/inclusa

# 11. Sincronitzar des del repositori remot al local

> $ git pull

# 12. Sincronitzar des del repositori local al remot

> $ git push

# 13. Evitar que GIT demane usuari i contrasenya

> $ git config --global credential.helper. store

La contrasenya del repositori remot queda magatzemada al fitxer `.git-credentials`

# 14. No guardar la contrasenya en disc

> $ git config --global credential.helper 'cache --timeout=3600'

Transcorreguda un hora tornarà a demanar la contrasenya.

# 15. Borrar branca i borrar-la del server

Objectiu: volem borrar la branca gh-pages

> $ git branch -d gh-pages           # elimina branca local

> $ git push origin :gh-pages        # elimina branca remota

# 16. Iniciar repositori en GITHub des de terminal amb el protocol `https://`

> echo "# repositori" >> README.md<br />
> git init<br />
> git add README.md<br />
> git commit -m "comentari"<br />
> git remote add origin https://github.com/usuari/repositori.git<br />
> git push -u origin master

# 17. Explicació

`echo`: Afegix la informació al fitxer, si no existeix el crea

`git init`: Inicia el repositori creant els arxius de rastreig a .git

`git add README.md`: Afegig l'arxiu README.md per tal que es rastrege

`git commit -m "comentari"`: Crea el punt d'emmagatzemmament del contigut actual, emmgatzema el contingut de del projecte establint fixant un punt, també afegeix un comentar

`git add remote add origin https://`: Afegeig repositori remot

`git push -u origin master`: publica el repositori local a la branca `master` remota

# 18. Publicar a un repositori existent a GITHub des de la línia de comandamentsamb el protocol `https://`

> git remote add origin https://github.com/usuari/repositori.git

> git push -u origin master

# 19. Iniciar repositori en GITHub des de terminal amb el protocol `ssh`

> echo "# repositori" >> README.md<br />
> git init<br />
> git add README.md<br />
> git commit -m "comentari"<br />
> git remote add origin git@github.com:usuari/repositori.git<br />
> git push -u origin master<br />

# 20. Publicar a un repositori existent a GITHub des de la línia de comandamentsamb el protocol `ssh`

> git remote add origin git@github.com:usuari/repositori.git

> git push -u origin master


# 21. Branques en GIT

Tots els projectes, per defecte, tenen la branca MASTER on, al final, acaben totls els desenvolupaments que fem.

Podem definir altra branca, per exemple, DEVELOP on anar fent tots els xicotets canvis que necessitem fer.

Per canviar de branca, per situar-nos a una altra branca

> $ git checkout -b develop

`checkout` → canvia de branca
`-b` → crea la branca


Quan arribem a un punt on tots els canvis que hem anat fent son estables i ens interessa que apareguen en la branca MASTER farem un **merge**.

Primer ens situem en la branca MASTER

> $ git checkout master

Ara li diguem que porte els canvis que hem fet a DEVELOP

> $ git merge develop

Ara tindrem una nova versió a la branca MASTER

Pot passar que hi hagen problemes al fer el `merge`, en cas que GIT no sàpiga distingir quinies són les líies bones ens ho preguntarà.


# 22. Etiquetes en GIT

Podem definir etiquetes per a gestionar versions del nostre codi o punts importants de desenvolupament, de forma que després ens siga fàcil identificar les fases de desenvolupament

> $ git tag -a v1.0 -m 'Versió 1.0'


# 23. Banques en GIT

Les branques són línies de treball que tenen un objectiu. Posem un exemple de diferents branques amb diferents objectius de fases del treball.

`MASTER`: branca principal on aniran tots els canvis finals, així que, en aquest cas podriem etiquetar diverses versions explicitant les fases V0.1, v0.2, v0.3, etc.

`DEVELOP`: branca on es realitzen canvis més xicotets, però també es proven. Pot tenir diverses subbranques.

`RELEASE`: branca on podem agrupar certs pasos endaavnt, quan está provada podrem incorporar-ho a MASTER.

	MASTER		RELEASE		DEVELOP
	X
	|
	|\
	| \ __→__→__→__→__→__→__→__→__→__→__ X
	|                                    ↓
	|                                    |
	|                                    |
	|                 X __←__←__←__←__ ← X
	|                /
	|               /
	|__←__←__←__←_ X
	X               

# 24. Si fallem podem tronar enrere

> $ git checkout --fitxer

Inclús podem dir "tot el que hem fet pins ara no val per a res"

> $ git fetch origin && git reset --hard origin/master

# 25. Canviar tot el contingut d'una branca

Sobreescrivim una branca a altra:

```bahs
git branch -m master old-master
git branch -m gh-pages master
git push -f origin master
```

`-m` renomena
` -f` força

# 26. GITHub

- [Iniciar repositori](https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/#platform-linux)

# 27. Fonts

- [git - la guia sencilla](http://rogerdudler.github.io/git-guide/index.es.html)
- [Become a git guru](https://www.atlassian.com/git/tutorials/)
- [Pro Git](https://git-scm.com/book/es/v1)
- [Cheat Sheets](http://cheat.errtheblog.com/s/git)
- [GIT - Tutorials Point](http://www.tutorialspoint.com/git/)
- [Documentació base](http://git-scm.com/doc)
- [Documentació base en espanyol](http://git-scm.com/book/es)
- [Guia ràpida de GIT](http://www.flx.cat/desenvolupament/2013/11/11/guia-rapida-git.html)
- [GIT Màgic](http://www-cs-students.stanford.edu/~blynn/gitmagic/intl/es/)

# 27. Video
* [GITHub en Camon - Murcia](https://vimeo.com/39829002)
* [Introduction to GIT with Scott Chacon of GITHub](https://www.youtube.com/watch?v=ZDR433b0HJY)
