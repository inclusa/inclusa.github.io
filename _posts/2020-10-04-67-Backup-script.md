---
layout: post # Sustituye el layout si lo usas uno diferente
title: 67 Backup script # Nombre generado automáticamente
---

Manera senzilla de fer un backup

```bash
#!/bin/bash
BACK=backup_$(date +%Y%m%d).tar.gz
cd /home/usuari/backup/directori_destí          # Sitúat al directori on vols deixar el backup
tar -czf $BACK /home/usuari/Documents/treball   # Executa el backup
```

