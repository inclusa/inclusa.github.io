---
layout: post
title: 09 Renomenar arxius
date:  2016-07-16 00:00:00
description: Procediment per renomenar de forma massiva arxius des del terminal.
---

Per tal de renomenar els arxius a sistemes operatius **GNU/Linux**.

```bash
#!/usr/bin/bash
# Utilitat per renomenar arxius amb extensió .markdown a .md

rename 's/\.markdown/\.md/' *.markdown
```
Altre exemple

Si tenim uns arxius amb extensió `.md` i volem canviar l'extensió de tots ells per l'extensió `.txt` caldrà escriure el següent comandament:

```bash
rename 's/\.md/\.txt/' *.md
```

D'aquesta manera el canviarà d'una sola vegada l'extensió de tots els arxius que tinguen l'extensió .md a .txt perquè li em dit que actua sobre tots els que tinguen aquesta extensió amb el final del comandament *.md

