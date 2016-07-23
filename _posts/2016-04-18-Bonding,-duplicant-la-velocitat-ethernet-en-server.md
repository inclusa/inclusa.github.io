---
layout: post
title: 06 Bonding, ethernet 2 Gigabits 
date: 2016-04-18 00:00:00
description: Utilització de dues targetes ethernet com una sola de forma que podem duplicar l'ample de banda en un server
---

# Definició

**Channel bonding** és una tècnica que consisteix en la utilització de dues targetes d'ethernet amb la finalitat de duplicar i balancejar la velocitat d'ethernet en servidors.

# Avantatges:

- Si una de les dues targetes es trenca, sempre queda l'altra.
- Es duplica l'ample de banda, així que duplicarem la velocitat.

# Passos

Instal·lem software per assignar interfaces de xarxa al mòdul que les enllaça

```
$ sudo apt-get install ifenslave
```

Creem un arxu de configuració de l'enllaç

```
$ sudo vim /etc/modprove.d/bondig.conf
```

Li afegim aquestes línies

```
alias bond0 bonding
optins bonding mode=0 miimon=100
```

El `mode=0` permeteix balancejar la càrrega i tolerància a errades, es poden utilitzar altres mòduls. L'altre paràmetre és el temps entre comprovacions de l'estat de la interface.

Seria bo desinstal·lar assistents com **Network Manager**.

Editem l'arxiu d'interfaces de xarxa

```
sudo vim /etc/network/interfaces
```

Comentem les línies de les interfaces amb un # a principi de línia, hauria de quedar així:

```
auto lo
iface lo inet loopback

auto bond0
iface bond0 inet static
address 192.168.1.240
gateway 192.168.1.1
netmask 255.255.255.0
slaves eth0 eth1
bond-mode 0
bond-miimon 100
```

Cal posar en `address` la nostra direcció i en `gateway` l'adreça del router.

Les dos últimes línies sols les posem en cas que no hagem creat l'arxiu /etc/modprobe.d/bonding.conf

Arramquem el servei

```
$ sudo modprobe bonding
$ sudo /etc/init.d/networking restart
```

# Fonts

- [El 64](http://el64.blogspot.com.es/2010/01/enlazar-dos-tarjetas-de-red-bonding.html)
- [Ubuntu Bonding](https://help.ubuntu.com/community/UbuntuBonding)

