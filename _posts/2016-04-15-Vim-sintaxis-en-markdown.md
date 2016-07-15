---
layout: post
title: 05 Sintaxis en Markdown
date: 2016-04-15 00:00:00
description: Per tal que Vim pinte el codi de Markdown correctament
---

Treballar amb l'editor [Vim](http://www.vim.org/) suposa aprendre a escriure en aquets entorn.

No és fàcil, al principi superar el temps i la paciència que hem d'invertir per tal d'aconseguir crear un entorn propici per treballar. Una de les característiques que em molestava molt és que canviara de color les llebres quan utilitzava cometes.

Per resoldre aquest problema vaig recòrrer a instal·lar les sintaxis que més sovint utilitzava, en el meu cas, **markdown**, **html**, **bash** i **python**.

Per tal que **Vim** colorejara els continguts escrits en markdown cal seguir aquests senzills passos:

1. Localitzem les instruccions i el codi font en la mateixa plana de [Vim](http://www.vim.org/scripts/script.php?script_id=1242) el repositori de [plasticboy](https://github.com/plasticboy/vim-markdown).
2. Cal tenir instal·lat el plugin [Patogen](https://github.com/tpope/vim-pathogen).
3. Clonem o descarreguem el repositori [plasticboy](https://github.com/plasticboy/vim-markdowni).
4. Ara descareguem el codi:

```
cd ~/.vim/bundle
git clone https://github.com/plasticboy/vim-markdown.git
```

Finalment activem el codi a l'arxiu `.vimrc`

```
autocmd BufNewFile,BufReadPost *.md set filetype=markdown
```
Tamquem totes les terminals i les tornem a obrir.

Així ja ens reconeixerà la sintaxi de **Markdown** de forma correcta.

