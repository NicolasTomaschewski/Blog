---
title: "Inspecionando namespaces de um container em execução"
description: "Como verificar os namespaces ativos de um processo container diretamente pelo /proc do kernel."
date: 2025-02-10
tags: ["linux", "containers", "namespaces", "debug"]
---

Para inspecionar os namespaces de um container em execução sem entrar nele:

```bash
# Encontrar o PID do processo principal do container
PID=$(docker inspect --format '{{.State.Pid}}' <container_id>)

# Listar os namespaces do processo
ls -la /proc/$PID/ns/
```

A saída mostra symlinks para cada namespace: `cgroup`, `ipc`, `mnt`, `net`, `pid`, `pid_for_children`, `time`, `uts`, `user`.

Dois processos que compartilham o mesmo namespace têm symlinks que apontam para o mesmo inode. Útil para verificar se dois containers estão realmente isolados ou compartilhando algum namespace (como acontece com `--network host`).

Aprendi isso ao depurar um problema onde dois containers inesperadamente conseguiam se comunicar sem a rede Docker.
