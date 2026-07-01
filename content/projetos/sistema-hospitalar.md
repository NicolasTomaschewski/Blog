---
title: "Sistema Hospitalar Acadêmico"
descricao: "Sistema de gestão hospitalar desenvolvido como projeto integrador de engenharia de software, com foco em modelagem de domínio e arquitetura em camadas."
tecnologias: ["Java", "Spring Boot", "PostgreSQL", "Docker", "React"]
status: "concluído"
periodo: "2023"
date: 2023-11-01
---

## Contexto

Projeto desenvolvido em equipe como trabalho integrador da graduação. O objetivo era construir um sistema de informação hospitalar funcional, aplicando na prática os conceitos de engenharia de software estudados ao longo do curso.

O domínio escolhido — gestão hospitalar — é rico em complexidade: múltiplos atores (pacientes, médicos, enfermeiros, administração), fluxos de negócio intrincados e requisitos de consistência de dados muito rígidos.

## Objetivo

Construir um sistema com as seguintes funcionalidades:

- Cadastro e gestão de pacientes
- Agendamento e controle de consultas
- Gestão de prontuários eletrônicos
- Controle de leitos e internações
- Relatórios administrativos

## Arquitetura

Adotamos uma arquitetura em camadas com separação clara de responsabilidades:

```
┌─────────────────────────────────────┐
│           Frontend (React)          │
├─────────────────────────────────────┤
│         API REST (Spring Boot)      │
│  ┌──────────┐  ┌─────────────────┐  │
│  │Controllers│  │   Services      │  │
│  └──────────┘  └─────────────────┘  │
│  ┌──────────────────────────────┐   │
│  │      Repositories (JPA)      │   │
│  └──────────────────────────────┘   │
├─────────────────────────────────────┤
│           PostgreSQL                │
└─────────────────────────────────────┘
```

O modelo de domínio foi elaborado cuidadosamente antes de qualquer linha de código. Identificamos as entidades principais, seus relacionamentos e as invariantes de negócio que precisavam ser garantidas em nível de aplicação e banco de dados.

## Desafios

O maior desafio não foi técnico: foi a gestão de inconsistências nos requisitos. Um sistema hospitalar tem regras de negócio complexas, e diferentes integrantes da equipe tinham interpretações diferentes do mesmo requisito.

Resolvemos isso adotando sessões de modelagem de domínio em conjunto antes de iniciar a implementação, usando técnicas de Event Storming simplificado para mapear os fluxos do sistema.

No lado técnico, o controle de concorrência em operações críticas (como a alocação de leitos) exigiu atenção especial. Implementamos pessimistic locking para operações de escrita em recursos compartilhados.

## Resultados

O sistema foi entregue com todas as funcionalidades planejadas, cobertura de testes unitários acima de 70% e documentação de API gerada via OpenAPI/Swagger.

A avaliação do projeto foi positiva, com destaque para a qualidade do modelo de domínio e a consistência da arquitetura.

## Aprendizados

Trabalhar em equipe em um sistema de médio porte me ensinou que a comunicação técnica é tão importante quanto o código em si. Decisões de arquitetura precisam ser documentadas e comunicadas para que todos do time possam tomar decisões locais consistentes com a visão global.

Também aprendi que a modelagem de domínio investe tempo no início para economizar muito mais tempo depois. A maioria dos bugs que encontramos em fases avançadas do projeto poderiam ter sido prevenidos com um modelo de domínio mais cuidadoso.
