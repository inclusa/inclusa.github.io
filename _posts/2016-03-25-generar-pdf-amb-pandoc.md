---
layout: post
title: 02 Generar PDF amb Pandoc
date: 2016-03-25 16:00:00
description: Procediment per generar PDF des de Markdown
---

[Pandoc](http://pandoc.org) és una utilitat creada per [John MacFarlane](http://johnmacfarlane.net/), professor de filosofia a la Universitat de California.

Podem utilitzar [pandoc](http://pandoc.org) per generar documents en molts formats. Actualment s'està veien el gran esforç de desenvolupar codi font, així com la necessitat de ferramentes que faciliten la generació de codi complexe.

D'aquesta manera podriem escriure un document en un llenguatge codificat molt senzill, com és [markdown](https://daringfireball.net/projects/markdown/), aquest llenguatge fou crear inicialment per [John Gruber](http://daringfireball.net/). Es tracta d'un llenguatge de programació que necessita una utilitat per generar documents estandars.

Algun del programari existen que utilitza aquest llenguatge:

- [Stackedit](https://stackedit.io/)
- [Dilinger](http://dillinger.io/)

Alguns dels tutorials per aprendre el llenguatge:

- [MarkdownTutorial](http://www.markdowntutorial.com/)
- [Blog de Joe Di Castro](http://joedicastro.com/pages/markdown.html)

D'aquesta manera, podriem crear un document en un processador de text pla com ara Vim, Emacs, TextEdit o Notepad.

	# Títol de primer nivell
	
	## Títol de segon nivell
	
	*cursiva*
	**negreta**
	~tatxat~
	>blockquote
	`code`
	[link](http://#)
	![imatge](http://#.image.png)
	

Per tal de generar el codi del fitxer que conté aquesta informació, que anomenarem input.md farem el següent:

	$ pandoc input.md -o output.pdf


D'aquesta manera obtindrem un fitxer en pdf, amb una formatació `standalone` bàsica.

En cas de que vullguerem utilitzar una [template](https://pandoc.org/demo/template.tex), en aquest cast de [latex](https://latex-project.org/intro.html) caldria primer obtenir-la i modificar-la al nostre gust. Podeu veure un exemple a l'[exemple número 14 de la pàgina de pandoc](https://pandoc.org/demos/example14.pdf). Primer obtindriem la *template*.

> Cal baixar la plantilla (template) i posar-la en el mateix directori on anem a generar el document final.

Amb aquest senzill comandament generariem un document *output.pdf* amb índex, enllaços i interns a partir de dos documents escrits en markdown *input1.md* i *input2.md*. Tot escrit en lletra de 12 punts.


	pandoc --template mytemplate.tex --toc -V fontsize=12pt -o output.pdf input1.md input2.md 

En cas de que vullguerem modificar la font caldria editar el fitxer *mytemplate.tex* i variar la font de la lletra així:

	\usepackage[default]{cantarell} %% Use option "defaultsans" to use cantarell as sans serif only

Així hem canviat la font de lletra *modern* per *cantarell* més pareguda a la que solem utilitzar en paper. Per revisar les fonts que es poden utilitzar cliqueu en el següent enllaç.

Per tal que tot funcione cal tenir instal·lades les fonts de lletra LaTeX a Ubuntu, el paquet [lextlive-fonts-extra](https://launchpad.net/ubuntu/trusty/+package/texlive-fonts-extra):

	$ sudo apt-get install texlive-fonts-extra

També cal tenir instal·lat LaTeX, però al tant, això ocupa 1 GB de disc dur.

