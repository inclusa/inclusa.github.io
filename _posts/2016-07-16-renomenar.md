---
layout: post
title: 09 Renomenar arxius
date:  2016-07-16 00:00:00
---

Per tal de renomenar els arxius a sistemes operatius **GNU/Linux**.

```bash
#!/usr/bin/bash
# Utilitat per renomenar arxius amb extensió .markdown a .md

rename 's/\.markdown/\.md/' *.markdown
```
