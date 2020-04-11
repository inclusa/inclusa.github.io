---
layout: post #
title: 63 Crear Manpages # Generat automàticament
date: 2020-04-11 # Data
description:  # Argument
keywords:  # Paraules clau
coments:  # Comentaris
---

En aquest post explicarem com crear una `man page` per a shell o python script sobre GNU Linux/Unix.

### Troff i Groff Macro

`Troff` és un sistema de processament de document desenvolupat per AT&T per al sistema operatiu Unix. Troff inclou comandaments anomenats macros que corren abans de posar en marxa el document. Aquests documents inclouen capçaleres i peus de pàgina, definits amb comandaments i generalment influint en el seu format. Els manuals de GNU/Linux estan formatats amb el paquet `groff`. `Groff` (GNU troff) es un software que llegeix text pla amb formats i comandaments.

### Estructrura

```
NAME
    Nom del comandament, funció i descripció.
SYNOPSIS
    Descripció del comentadament, quin és el seu objectiu.
DESCRIPTION
    Descripció e les funcionalitats.
EXAMPLES
    Alguns dels exemples d'ús.
SEE ALSO
    Llista de comandaments relatant les seues funcions.
BUGS
    Llista de bugs coneguts.
AUTHOR
    Especificant la informació de contacte.
COPYRIGHT
    Especificar la informació de la llicència.
```

Es poden afegir altres seccions com EXIT STATUS, ENVIRONMENT, FILES, HISTORY, etc. La tabla que mostra les seccions es pot accedir amb el comandament `man man`.

### Localització

El sistema manté les pàgines dels manuals en aquest directori `/usr/share/man/`.

Es pot accedir així:

```
cp /usr/share/man/man1
ls -l
zcat ls.1.gz
```

### Adaptació de la localització de pàgines Man

Es recomana que les pàgines man romanguen al directori `/usr/local/man`. Pots configurar el camí de la cerca a l'arxiu `/etc/man.config`:

```
MANPATH /usr/man
MANPATH /usr/share/man
MANPATH /usr/local/man
MANPATH /usr/local/share/man
MANPATH /usr/X11R6/man
```

Els detalls es poden consultar a `man manpath`.

### Crear Man Pages

```
vim nuseradd
```

Escrivim:

```
.\" Manpage for nuseradd.
.\" Contact vivek@nixcraft.net.in to correct errors or typos.
.TH man 8 "06 May 2010" "1.0" "nuseradd man page"
.SH NAME
nuseradd \- create a new LDAP user 
.SH SYNOPSIS
nuseradd [USERNAME]
.SH DESCRIPTION
nuseradd is high level shell program for adding users to LDAP server.  On Debian, administrators should usually use nuseradd.debian(8) instead.
.SH OPTIONS
The nuseradd does not take any options. However, you can supply username.
.SH SEE ALSO
useradd(8), passwd(5), nuseradd.debian(8) 
.SH BUGS
No known bugs.
.SH AUTHOR
Vivek Gite (vivek@nixcraft.net.in)
```

Per visualitzar:

```
man ./nuseradd
```

El codi de macro `.TH` introdueix un manual, per exemple, títol o secció. Així sabent això podem accedir a la descripció dels macros:

```
man 7 mdoc
```

### Instal·lar Man Page

```
cp nuseradd /usr/local/man/man8/nuseradd.1
gzip /usr/local/man/man8/nuseradd.1
man nuseradd
```

També es pot instal·lar amb aquests scripts:

```
install -g 0 -o 0 -m 0644 nuseradd.1 /usr/local/man/man8/
gzip /usr/local/man/man8/nuseradd.1
```

### Referències

- [nixCraft](https://www.cyberciti.biz/faq/linux-unix-creating-a-manpage/)
- [GNU Troff (Groff)](https://www.gnu.org/software/groff/)
