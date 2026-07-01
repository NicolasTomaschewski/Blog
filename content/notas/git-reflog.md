---
title: "git reflog salva vidas"
description: "Quando você faz git reset --hard e acha que perdeu o trabalho."
date: 2025-01-15
tags: ["git", "debug", "ferramentas"]
---

`git reflog` mantém um log de todos os movimentos do HEAD, incluindo aqueles que não aparecem no `git log`.

```bash
git reflog
# a1b2c3d HEAD@{0}: reset: moving to HEAD~1
# e4f5g6h HEAD@{1}: commit: feature: adicionar autenticação
# ...

# Recuperar o commit que você achou que perdeu
git checkout e4f5g6h
# ou
git reset --hard e4f5g6h
```

O reflog mantém entradas por padrão por 90 dias. Aprendi isso depois de fazer um `reset --hard` no momento errado.
