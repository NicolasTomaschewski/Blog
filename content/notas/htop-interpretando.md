---
title: "Interpretando htop: o que cada coluna realmente significa"
description: "Ler htop parece óbvio até você precisar diagnosticar um problema de performance real."
date: 2024-12-03
tags: ["linux", "performance", "observabilidade", "ferramentas"]
---

Colunas que frequentemente causam confusão:

**VIRT** — memória virtual total alocada pelo processo. Inclui regiões mapeadas mas não necessariamente físicas. Raramente é o número que importa.

**RES** — memória física residente. O que o processo está de fato usando na RAM. Este é o número relevante para avaliar pressão de memória.

**SHR** — porção de RES que é compartilhada com outros processos (bibliotecas compartilhadas, por exemplo). RES - SHR = memória exclusiva do processo.

**%CPU** — porcentagem de um único núcleo. Em sistemas multi-core, um processo pode aparecer com 400% se usar 4 núcleos completamente.

Para ver consumo real de memória de um processo:

```bash
# Memória privada do processo
cat /proc/<pid>/status | grep -E "VmRSS|VmPSS|RssAnon"
```

`RssAnon` (memória anônima residente) é frequentemente a métrica mais honesta para diagnosticar memory leaks.
