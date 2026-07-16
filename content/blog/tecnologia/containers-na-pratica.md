---
draft: true
title: "Containers na prática: do conceito à produção"
description: "Como minha compreensão de containers evoluiu de 'Docker é um jeito de empacotar aplicações' para entender os mecanismos que tornam isso possível."
date: 2024-11-05
categoria: "tecnologia"
tags: ["docker", "containers", "linux", "namespaces", "cgroups", "infraestrutura"]
---

Durante muito tempo, containers foram para mim uma caixa preta conveniente. Eu entendia o _o que_ — isolar processos, empacotar dependências, garantir reprodutibilidade — mas não o _como_.

Isso mudou quando precisei depurar um problema de performance em um container que consumia mais CPU do que deveria. Para entender o problema, precisei entender os mecanismos subjacentes.

## O que um container realmente é

Um container Linux não é uma máquina virtual. Não há hypervisor, não há kernel separado. O que existe são dois mecanismos do kernel Linux trabalhando juntos:

**Namespaces** — controlam o que um processo pode _ver_. Um processo dentro de um namespace de PID enxerga apenas os processos do seu namespace. Um processo dentro de um namespace de rede enxerga apenas as interfaces de rede do seu namespace. O sistema de arquivos, os usuários, os hostnames — tudo pode ser isolado via namespaces.

**cgroups (Control Groups)** — controlam o que um processo pode _usar_. CPU, memória, I/O de disco, largura de banda de rede — os cgroups estabelecem limites e monitoram o consumo de recursos.

Um container é, na essência, um conjunto de processos em namespaces isolados com limites de recursos impostos por cgroups. O Docker e outros runtimes são ferramentas de gerenciamento que orquestram esses mecanismos.

## Depurando o problema de CPU

Voltando ao problema original: um container que consumia CPU inesperadamente.

```bash
# Verificar processos dentro do container
docker exec -it <container_id> top

# Ver os cgroups do container no host
cat /sys/fs/cgroup/cpu/docker/<container_id>/cpu.stat

# Verificar limites configurados
docker inspect <container_id> | grep -i cpu
```

O problema estava na ausência de limite de CPU configurado. O container, sem restrições de cgroup, competia livremente por recursos com outros processos do host. A solução foi configurar `--cpus` no momento da inicialização:

```bash
docker run --cpus="1.5" minha-aplicacao
```

Entender que o `--cpus` do Docker se traduz em configurações de cgroup tornou o diagnóstico direto.

## Imagens e layers

Outro aspecto que frequentemente é tratado como mágica: o sistema de layers das imagens Docker.

Cada instrução no `Dockerfile` cria uma layer — uma diferença (diff) do sistema de arquivos em relação à camada anterior. Essas layers são imutáveis e podem ser compartilhadas entre imagens.

```dockerfile
# Layer 1: imagem base (compartilhada com outras imagens que usam python:3.12-slim)
FROM python:3.12-slim

# Layer 2: dependências do sistema (muda raramente)
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

# Layer 3: dependências Python (muda quando requirements.txt muda)
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Layer 4: código da aplicação (muda frequentemente)
COPY . .

CMD ["python", "app.py"]
```

A ordem importa. Colocar o que muda com menos frequência no início maximiza o reaproveitamento de cache durante builds.

## O que aprendi com isso

Minha compreensão atual é que abstrações bem construídas como o Docker são valiosas exatamente porque nos permitem trabalhar em um nível mais alto sem precisar pensar constantemente nos detalhes de implementação.

Mas quando algo dá errado, descer um nível de abstração e entender o que está acontecendo no kernel é frequentemente o caminho mais direto para a solução.

Namespaces e cgroups não são detalhes de implementação que você precisa memorizar para o dia a dia. São os fundamentos que explicam o comportamento que você observa — e que se tornam indispensáveis quando o comportamento não é o esperado.
