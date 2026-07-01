---
title: "O Cisne Negro — o que não sabemos que não sabemos"
description: "Nassim Taleb e o problema da incerteza que não conseguimos quantificar. Uma leitura que mudou como penso sobre previsão e robustez de sistemas."
date: 2024-08-14
categoria: "leituras"
tags: ["taleb", "incerteza", "probabilidade", "sistemas", "epistemologia"]
---

*O Cisne Negro* de Nassim Taleb não é um livro sobre eventos raros. É um livro sobre os limites do nosso conhecimento — especificamente, sobre a categoria de ignorância que não reconhecemos como tal.

A ideia central é simples: antes de 1697, todos os europeus acreditavam que cisnes eram brancos. Isso não era uma crença irresponsável — era baseada em evidência empírica extensiva. Até que exploradores chegaram à Austrália e encontraram cisnes negros.

O problema não era a conclusão. Era a confiança na conclusão diante de uma amostragem fundamentalmente limitada.

## O que ficou

Taleb distingue dois domínios: Mediocristão e Extremistão.

No Mediocristão, as variáveis têm distribuições com caudas finas. A altura humana é um exemplo: ninguém tem dois metros e meio, ninguém tem vinte centímetros. A média é representativa, os desvios são limitados. A lei dos grandes números funciona bem.

No Extremistão, eventos extremos dominam. Riqueza, impacto de livros, guerras, pandemias. Uma única observação pode ser maior do que a soma de todas as anteriores. Médias enganam. Modelos que assumem distribuições normais falham exatamente quando mais importaria que não falhassem.

A crise financeira de 2008 foi um Cisne Negro? Depende de quem você pergunta. Para quem modelava risco usando distribuições que subestimavam caudas gordas — sim. Para quem entendeu que o sistema financeiro estava acumulando fragilidade invisível — não exatamente uma surpresa.

## A aplicação que mais me interessa

O que isso tem a ver com engenharia de sistemas?

Tudo. A maioria dos sistemas críticos falha de formas que não foram previstas nos requisitos. Não porque os engenheiros foram descuidados, mas porque estavam modelando com base no espaço de falhas conhecido — e sistemas reais falham no espaço de falhas não imaginado.

A resposta de Taleb é construir sistemas robustos, até antifrágeis — que se beneficiam de volatilidade em vez de quebrarem diante dela. Em termos práticos: redundância, capacidade de recuperação, ausência de pontos únicos de falha, operação conservadora em condições normais para ter margem quando o inesperado acontece.

Isso ressoa com a filosofia Unix de ferramentas pequenas e composáveis, com o princípio de menor privilégio em segurança, com a preferência por sistemas distribuídos que degradam graciosamente.

## Uma tensão que não foi resolvida

O livro tem uma tensão que Taleb não resolve completamente: se Cisnes Negros são por definição imprevisíveis, como exatamente nos preparamos para eles?

A resposta parcial é: não prevendo eventos específicos, mas construindo sistemas que toleram surpresas em geral. Isso é menos satisfatório do que gostaríamos — mas provavelmente é o melhor que podemos fazer.

Minha compreensão após esta leitura é que a humildade epistêmica não é um luxo filosófico. É uma propriedade de engenharia. Sistemas projetados por pessoas que sabem o que não sabem tendem a falhar de formas mais toleráveis do que sistemas projetados por pessoas que acreditam que mapearam o espaço completo de possibilidades.
