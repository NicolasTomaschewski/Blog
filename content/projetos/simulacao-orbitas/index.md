---
title: "Simulação que Mostra a Troca de Órbitas de um Satélite"
description: "Simulação Computacional sobre a Troca de Órbitas de um Satélite Artificial"
tecnologias: ["Python", "Física", "Matemática", "Manobra de Hohmann", "Simulação Computacional"]
status: "Concluído"
periodo: "ago/2023 - ago/2024"
repositorio: "https://github.com/NicolasTomaschewski/Simulacao-Satelites"
date: 2026-07-15
---

## Contexto

Este foi o meu **Projeto de Iniciação Científica** na faculdade de engenharia da computação. O objetivo foi criar simulações em Python que exibam graficamente a troca de órbitas de um satélite que sai de uma órbita mais interna e atinge uma órbita mais externa em relação ao planeta. A simulação foi baseada na **Manobra de Hohmann**.

## Objetivo

Desenvolver uma análise detalhada da manobra de Hohmann, utilizando abordagens analíticas e computacionais. O projeto visa calcular e simular as trajetórias e variações de velocidade envolvidas na manobra, proporcionando uma compreensão aprofundada dos princípios que regem a transferência orbital eficiente entre duas órbitas circulares.

## O que é a manobra de Hohmann

A manobra de Hohmann é uma técnica amplamente utilizada para transferir espaçonaves entre duas órbitas circulares com raios diferentes. Este procedimento é considerado energeticamente eficiente e envolve dois impulsos: um para transferir a espaçonave para uma órbita elíptica de transferência e outro para inseri-la na órbita circular final. Assim a diferença de velocidades no periastro e apoastro entre as órbitas circulares (inicial e final) e a órbita elíptica intermédia é exatamente o impulso necessário.

### Como a manobra funciona matematicamente?

Essa é a trajetória que o satélite descreve ao longo da manobra:

{{< figure src="image.png" caption="Geometria da manobra: órbita inicial de raio R (verde), elipse de transferência (amarelo) e órbita final de raio R' (vermelho), com os impulsos Δv e Δv' aplicados no periastro e no apoastro." >}}

Essa é a velocidade que o satélite atinge após o primeiro impulso:

{{< figure src="image-1.png" caption="Velocidade ΔV do primeiro impulso, aplicado na órbita inicial de raio R para inserir o satélite na elipse de transferência." >}}

Essa é a velocidade que o satélite atinge após o segundo impulso:

{{< figure src="image-2.png" caption="Velocidade ΔV' do segundo impulso, aplicado ao final da elipse de transferência para circularizar a órbita no raio R'." >}}

Esse é o tempo total que a manobra demanda:

{{< figure src="image-3.png" caption="Tempo total de transferência t, em função do período orbital T₁ da órbita inicial." >}}

## Resultados

O trabalho evoluiu em versões sucessivas, cada uma acrescentando uma camada de complexidade sobre a anterior:

- **Protótipo** — A primeira versão do trabalho consiste apenas no cálculo das três equações acima no próprio terminal.
- **Órbita em 2D — Coordenadas Cartesianas** — Aqui é gerada uma imagem da manobra em coordenadas cartesianas baseada nos valores inseridos pelo usuário.

{{< figure src="image-4.png" width="360" caption="Manobra de Hohmann em coordenadas cartesianas: órbita inicial (1, ciano), elipse de transferência (2, amarelo) e órbita final (3, vermelho)." >}}

- **Órbita em 2D — Coordenadas Polares** — Aqui os dois trabalhos anteriores são unidos. O usuário é consultado sobre alguns parâmetros importantes, e os cálculos são apresentados junto com uma imagem da manobra em coordenadas polares.

{{< figure src="image-5.png" caption="Manobra de Hohmann em coordenadas polares, mostrando órbita inicial, órbita intermediária de transferência e órbita final em torno da Terra." >}}

- **Órbita em 3D** — Aqui foi feito um protótipo de como seria visualizar a manobra por vários ângulos. Essa versão permite que o usuário rotacione a manobra com o mouse.
- **Múltiplas Trocas** — Aqui o objetivo foi simular uma prática real da indústria aeroespacial. Via de regra, a maior preocupação dessa manobra é gastar o mínimo de combustível possível, mesmo que isso faça com que leve muito mais tempo. Para isso são feitas várias manobras até que o resultado final seja atingido, e o usuário pode escolher quantas manobras intermediárias vão acontecer. Essa foi considerada a versão definitiva do trabalho:

{{< figure src="image-6.png" caption="Captura de tela da simulação mostrando a troca de órbitas de uma baixa para uma média usando a técnica de múltiplas trocas." >}}

## Aprendizados

Ao longo desse trabalho pude aprender muito com o meu professor Ednardo a respeito de física, matemática, metodologia científica e escrita científica. No nível prático, pude exercitar muito a minha programação em Python, além de conhecer algumas bibliotecas novas como o tkinter, matplotlib e numpy.

## Artigo e Código

O trabalho foi publicado pelo Ceub e pode ser acessado [neste link →](https://www.publicacoes.uniceub.br/pic/article/view/9916).

Todos os códigos desenvolvidos estão disponíveis no [GitHub →](https://github.com/NicolasTomaschewski/Simulacao-Satelites).