---
layout: post # Sustituye el layout si lo usas uno diferente
title: 71 Certificat Digital # Nombre generado automáticamente
---

Per tal de signar amb certificat digital mirar aquest post de l'[Atareao](https://www.atareao.es/como/firma-digital-en-ubuntu/).

Per signar per terminal:

```bash
AutoFirma sign -i entrada.pdf -o eixida.pdf -store pkcs12:/home/usuari/Escriptori/certificat.p12 -alias firma -password lameuacontrasenya
```
Si volem signar més d'un document utilitzarem aquest script:

```bash
for i in entrada_*.pdf; do AutoFirma sign -i $i -o ${i/.pdf/}_signed.pdf -store pkcs12:/home/usuari/Escriptori/certificat.p12 -alias firma -password lameuacontrasenya; done
```


Per tal de comprovar la signatura per terminal, des de Debian, Ubuntu, cal instal·lar el paquet:

```bash
sudo apt install poppler-utils
```

Dins d'aquest paquet s'inclou la utilitat `pdfsig`, la utilitzarem per tal de visualitzar si el documen en PDF ha estat signat.

```bash
pdfsig arxiu.pdf
```

Això ens dóna aquesta informació:

```bash
Digital Signature Info of: arxiu.pdf
Signature #1:
  - Signer Certificate Common Name: PEPITO GRILLO GRILLO - NIF:00000000A
  - Signer full Distinguished Name: C=ES,O=ACCV,OU=CIUDADANOS,SN=GRILLO GRILLO,givenName=PEPITO,serialNumber=00000000A,CN=PEPITO GRILLO GRILLO - NIF:00000000A
  - Signing Time: Mar 10 2021 09:54:29
  - Signing Hash Algorithm: SHA-256
  - Signature Type: ETSI.CAdES.detached
  - Signed Ranges: [0 - 51775], [70945 - 133946]
  - Total document signed
  - Signature Validation: Signature is Valid.
  - Certificate Validation: Certificate is Trusted.
```
