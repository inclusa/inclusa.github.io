---
layout: post
title: 07 SSH missatge de benvinguda
date:  2016-05-01 00:00:00
description: Missatge de benvinguda quan et connectes a ssh.
---

Quan et connectes per `ssh` a moltes màquines cal identificar-les per tal d'estar segur què fas en cada màquina. Per fer-ho una manera efectiva caldrà posar un arxiu en aquest lloc:

```bash
/etc/update-motd/
```

Aquests arxius que romanen ací porten numeració davant, doncs cal respectar-la i afegir-ne una.

Com a model agafem aquest arxiu de **LliureX 15.05** `/etc/update-motd/61-lliurex`

```bash
#!/bin/bash
LANG=es_ES.UTF-8
TERM=xterm
export LANG 
export TERM
#VER=`lsb_release -ds`
#CAL=`cal`
HORA=`date +%r`
UPTIME=`uptime`
IMG=`n4d-client -c LmdImageManager -m getImageList`
ORD=`n4d-client -c LlxBootManager -m getBootOrder`
VER=`cat /usr/share/lliurex-cdd/version`

###########################
##DETECCION DE MEMORIA#############
detectmem () {
	hw_mem=0
	free_mem=0
	human=1024
	mem_info=$(</proc/meminfo)
	mem_info=$(echo $(echo $(mem_info=${mem_info// /}; echo ${mem_info//kB/})))
	for m in $mem_info; do
		if [[ ${m//:*} = MemTotal ]]; then
			memtotal=${m//*:}
		fi

		if [[ ${m//:*} = MemFree ]]; then
			memfree=${m//*:}
		fi

		if [[ ${m//:*} = Buffers ]]; then
			membuffer=${m//*:}
		fi

		if [[ ${m//:*} = Cached ]]; then
			memcached=${m//*:}
		fi
	done

	usedmem="$(((($memtotal - $memfree) - $membuffer - $memcached) / $human))"
	totalmem="$(($memtotal / $human))"
	mem="${usedmem}MiB / ${totalmem}MiB"
}
#####FIN DETECCION DE MEMORIA

###############################
#########DETECCION DE LA CPU#######

detectcpu () {
	REGEXP="-r"
	cpu=$(awk 'BEGIN{FS=":"} /model name/ { print $2; exit }' /proc/cpuinfo | sed 's/ @/\n/' | head -1)
	cpun=$(grep "physical id" /proc/cpuinfo | sort | uniq | wc -l)
	if [ -z "$cpu" ]; then
		cpu=$(awk 'BEGIN{FS=":"} /Hardware/ { print $2; exit }' /proc/cpuinfo)
	fi
	if [ -z "$cpu" ]; then
		cpu=$(awk 'BEGIN{FS=":"} /^cpu/ { gsub(/  +/," ",$2); print $2; exit}' /proc/cpuinfo | sed 's/, altivec supported//;s/^ //')
		if [[ $cpu =~ ^(PPC)*9.+ ]]; then
			model="IBM PowerPC G5 "
		elif [[ $cpu =~ 740/750 ]]; then
			model="IBM PowerPC G3 "
		elif [[ $cpu =~ ^74.+ ]]; then
			model="Motorola PowerPC G4 "
		elif [[ "$(cat /proc/cpuinfo)" =~ "BCM2708" ]]; then
			model="Broadcom BCM2835 ARM1176JZF-S"
		else
			model="IBM PowerPC G3 "
		fi
		cpu="${model}${cpu}"
	fi
	loc="/sys/devices/system/cpu/cpu0/cpufreq"
	if [ -f ${loc}/bios_limit ];then
		cpu_mhz=$(awk '{print $1/1000}' "${loc}/bios_limit")
	elif [ -f $loc/scaling_max_freq ];then
		cpu_mhz=$(awk '{print $1/1000}' "${loc}/scaling_max_freq")
	else
		cpu_mhz=$(awk -F':' '/cpu MHz/{ print int($2+.5) }' /proc/cpuinfo | head -n 1)
	fi
	if [ -n "$cpu_mhz" ];then
		if [ $(echo $cpu_mhz | cut -d. -f1) -gt 999 ];then
			cpu_ghz=$(awk '{print $1/1000}' <<< "${cpu_mhz}")
			cpu="$cpu @ ${cpu_ghz}GHz"
		else
			cpu="$cpu @ ${cpu_mhz}MHz"
		fi
	fi
        if [[ "${cpun}" -gt "1" ]]; then
               	cpu=$(sed $REGEXP 's/\([tT][mM]\)|\([Rr]\)|[pP]rocessor//g' <<< "${cpun}x ${cpu}" | xargs)
        else
               	cpu=$(sed $REGEXP 's/\([tT][mM]\)|\([Rr]\)|[pP]rocessor//g' <<< "${cpu}" | xargs)
        fi
}
############### CPU DETECCION FIN


####AVERIGUAMOS EL TIPO DE CLIENTE LLIUREX
lliurex-version > /tmp/test-mod.txt
echo $LTSP_FATCLIENT > /tmp/test-mod-fat.txt
if [ `grep server /tmp/test-mod.txt -c` != 0 ]; then
	if [ `echo x$DISPLAY | cut -d : -f 1` = 'x' ]; then
		SOY=Servidor
	else
		SOY=Ligero
	fi
else
	if [ `grep client /tmp/test-mod.txt -c ` != 0 ]; then
		#EJECUTA=`echo $LTSP_FATCLIENT | grep true| wc -l`
		EJECUTA=$(grep "true" /tmp/test-mod-fat.txt -c)
		if [ "$EJECUTA" != "0" ];then
			SOY=Semiligero
		else
			SOY=Pesado
		fi
	else
		SOY=Desktop
	fi
fi

############################
#####AVERIGUAMOS LA ARQUITECTURA
############################

if [ `uname -m | grep "x86_64" -c` == 0 ]; then
	ARQ="32 Bits"
else
	ARQ="64 Bits"
fi


############################
###DATOS DE MAQUINA ORIGEN
############################
IMG2=`echo $IMG|sed 's/\[\|\]//g'|sed 's/"//g'|sed 's/,/ /g'|sed 's/.json//g'`
ORD2=`echo $ORD|sed 's/\[\|\]//g'|sed 's/"//g'|sed 's/,/ /g'|sed "s/'//g"`

#CPU=`cat /proc/cpuinfo | grep 'model name' | cut -c 14-42 | uniq `

#MEM=`grep MemTotal /proc/meminfo | awk '{$1=$2/(1024); print $1,"MB";}'`

####DETECTAMOS LA MEMORIA FISICA Y USADA, ASI COMO LA CPU######
detectmem
detectcpu


echo 
echo "	-CLIENTE: $SOY"
echo "	-VERSION: $VER"
echo "	-ARQUITECTURA: $ARQ"
echo "	-CPU: $cpu"
echo "	-RAM: $mem"
if [ "$SOY" = "Server" ]; then
	DF=`df -h /net|tail -1|awk '{print $5}'`
	echo "	-Espacio ocupado en /net: $DF"
	echo "	-Imagenes LTSP disponibles: $IMG2"
	echo "	-Orden de arranque menu pxe: $ORD2"
	echo 
fi
echo 
echo Hora actual: $UPTIME

echo SERVER AULA LLIUREX 01

```
