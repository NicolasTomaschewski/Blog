---
title: "Sistema de Monitoramento de Sinais Vitais"
description: "Hardware e Software combinados para monitorar BPM, SpO2 e Temperatura Corporal e gerar relatórios com IA."
tecnologias: ["Python", "ESP32", "Flask", "MySQL", "API Gemini"]
status: "Concluído"
periodo: "set/2025 - jun/2026"
repositorio: "https://github.com/NicolasTomaschewski/TCC-Monitor-de-Saude"
date: 2026-06-23
---

## Contexto

Este foi o meu **Trabalho de Conclusão de Curso** em **Engenharia da Computação**. O objetivo foi contemplar as principais áreas de atuação de um engenheiro da computação construindo um **MVP completo** que envolvesse **programação web**, **eletrônica** e **programação de sistema embarcado**.

## Objetivo

O objetivo deste trabalho é desenvolver um sistema de monitoramento remoto de parâmetros básicos de saúde, capaz de coletar dados fisiológicos de um usuário por meio de **sensores biométricos** conectados a um **microcontrolador** e transmiti-los pela rede **Wi-Fi** para um servidor. Os dados são apresentados em uma interface web com visualização em tempo real, alertas clínicos e geração de relatório através de inteligência artificial generativa.

## Arquitetura

O sistema foi estruturado em três camadas independentes:

**Eletrônica** — Sensores **MAX30102** e **MLX90614** associados a um **ESP32** são responsáveis por aferir respectivamente **BPM/SpO2** e **Temperatura Corporal**.

**Firmware** — O código que controla o sistema embarcado segue um passo a passo simples: conexão com a rede Wi-Fi desejada, inicialização dos sensores, leitura dos sinais vitais, validação dos dados lidos, envio para o servidor.

**Dashboard Web** — Ao acessar com login e senha o usuário tem acesso a duas telas principais: uma tela com três gráficos — um por parâmetro — junto com **estatísticas** gerais, e uma tela de geração de **diagnóstico/relatório** com **inteligência artificial generativa**.

## Desafios

**Transmissão via Wi-Fi** — O principal desafio foi enviar os dados lidos pelos sensores para o servidor via Wi-Fi. Fazer isso por Bluetooth seria mais simples, mas o objetivo era viabilizar o monitoramento remoto — permitindo, por exemplo, que um médico acompanhe o paciente a distância.

**IP dinâmico** — Durante o desenvolvimento, ficou evidente que o **IP** do servidor precisava estar fixo no código do firmware. O problema é que esse endereço muda com frequência em redes domésticas. A solução identificada foi hospedar o servidor em uma **VPS**, onde o IP se mantém fixo — o que ficou como ponto de melhoria para versões futuras do projeto.

**Ligações eletrônicas** — Além disso, foi necessário soldar com muito cuidado os sensores na placa. Esse tipo de conexão sempre é desafiador, mas dessa vez foi ainda mais — trata-se de sensores muito pequenos e sensíveis, sem reposição caso algum fosse danificado.

## Resultados

Ao longo dos meses os resultados atingidos foram:

**Hardware:**

- Placa de circuito conectando o ESP32 aos dois sensores
- Case impresso em **3D** para proteção da placa e arremate

**Dashboard:**
- Tela de Login
- Tela principal com gráficos e estatísticas
- Tela de Diagnóstico com IA Generativa e geração de relatório
- Histórico dos dados coletados nas últimas 24 horas no banco de dados

{{< figure src="image-1.png" caption="Tela principal do dashboard: gráficos em tempo real de BPM, SpO2 e temperatura corporal, com estatísticas gerais." >}}

## Aprendizados

**Sistemas embarcados e IoT** — Foi meu primeiro contato real com programação de sistemas embarcados. Entender as restrições de hardware — memória limitada, ciclos de leitura, timing dos sensores — me fez pensar de forma diferente sobre software. Fazer o ESP32 se comunicar de forma estável com o servidor pela rede foi onde teoria e prática mais se distanciaram.

**Construir um MVP completo** — Aprendi que construir um produto funcional de ponta a ponta é diferente de dominar cada camada isoladamente. As decisões mais difíceis não foram técnicas — foram sobre o que deixar de fora para entregar algo que realmente funcionasse.

**Servidor Flask** — Subir e estruturar um servidor web pela primeira vez me mostrou na prática como funciona a comunicação entre cliente e servidor, rotas, autenticação e persistência de dados. O que parecia abstrato em aula ficou concreto quando o ESP32 começou a enviar dados reais para a API.

**Escrita técnica** — Desenvolver o artigo foi um aprendizado à parte. Estruturar o que foi construído em linguagem acadêmica exige clareza sobre o que realmente foi feito — e expõe rapidamente o que ainda não está bem compreendido.

**Apresentação** — Apresentar o trabalho diversas vezes para bancas e avaliadores me ensinou a explicar sistemas técnicos para públicos diferentes, ajustando o nível de detalhe conforme o interlocutor.

## Artigo Desenvolvido

Ao longo do trabalho o seguinte artigo foi desenvolvido mostrando tudo o que foi estudado e desenvolvido:

[Acessar artigo →](https://drive.google.com/file/d/1uCWhN1wQlHTRWaCt629nRY2J_msV9DOa/view?usp=sharing)

Inclusive fico muito feliz em ter vencido o prêmio Projeto Destaque do Ceub na categoria Completude! Agradeço a todos que prestigiaram o trabalho, ao Ceub e ao meu professor Molina pela orientação.

{{< figure src="image.png" width="360" caption="Recebendo o prêmio de Projeto Destaque do Ceub, categoria Completude." >}}

<div class="callout">
  <p class="callout-label">Aviso</p>
  <p>Este trabalho não visa substituir um médico. Trata-se de um experimento acadêmico.</p>
</div>