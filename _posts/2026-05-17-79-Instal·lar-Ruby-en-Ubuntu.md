---
layout: post # Sustituye el layout si lo usas uno diferente
title: 79 Instal·lar Ruby en Ubuntu # Nombre generado automáticamente
---

Per instal·lar Ruby 4 a Ubuntu 26.04 Resolute Racoon cal seguir la aquesta seqüència de comandaments:

```bash
sudo apt update
sudo apt install build-essential rustc libssl-dev libyaml-dev zlib1g-dev libgmp-dev
```

Ara instal·lem el gestor de versions [Mise](https://mise.jdx.dev/getting-started.html). Això facilita l'actualització de Ruby i el canvi entre versions.

```bash
curl https://mise.run | sh
echo 'eval "$(~/.local/bin/mise activate)"' >> ~/.bashrc
source ~/.bashrc
mise settings ruby.compile=false
```

Llavors instal·lem Ruby amb Mise.

```bash
mise use --global ruby4
```

Confirmem la versió de Ruby instal·lada.

```bash
ruby --version
```
Actualitzem RubyGems.

```bash
gem update --system
```
