---
draft: true
title: "Legislações relevantes para a minha área de TI"
description: "Quais são as leis que um bom engenheiro da computação deve dominar?"
date: 2026-08-26
categoria: "reflexoes"
tags: ["Legislação", "Leis", "LGPD"]
---

Recentemente conversei com algumas pessoas e cheguei à conclusão que estava na hora de dominar quais leis brasileiras são relevantes para um profissional de TI. Vemos cada vez mais notícias e polêmicas a respeito do mundo da tecnologia e eu sinto que tenho a obrigação de entender o que está acontecendo para ajudar as pessoas e para executar o meu trabalho sempre dentro das regras.

**[COMPLETAR: que conversa foi essa? O que te fez perceber que precisava estudar isso — uma dúvida de cliente da IronFrame, uma notícia, uma discussão na faculdade?]**

Não sou advogado, e este texto não é aconselhamento jurídico. É o registro do que entendi até agora, olhando pela lente de quem projeta, desenvolve e opera sistemas.

Em ordem cronológica, as leis brasileiras relevantes para a TI são:

## Código de Defesa do Consumidor — Lei nº 8.078/1990

É anterior à internet comercial no Brasil, mas vale para qualquer sistema que venda algo a um consumidor final. Em 2013, o Decreto nº 7.962 regulamentou o CDC para o comércio eletrônico.

**Na prática, para quem é de TI:** um e-commerce precisa exibir de forma clara a identificação da empresa (razão social, CNPJ, endereço), o preço total com frete e as condições da oferta, além de permitir o **direito de arrependimento** — o cliente pode desistir de uma compra feita pela internet em até 7 dias, e o sistema precisa oferecer um caminho para isso.

## Lei do Software — Lei nº 9.609/1998

Programa de computador é protegido como obra intelectual, pelo regime de direito autoral (a Lei nº 9.610/1998, de Direitos Autorais, se aplica de forma complementar). A proteção dura 50 anos e não depende de registro — registrar no INPI é opcional, mas ajuda a provar a autoria.

**Na prática, para quem é de TI:** a pergunta mais importante que essa lei responde é *de quem é o código que eu escrevo?*

- Se o software foi desenvolvido durante um contrato de trabalho ou de prestação de serviço cujo objeto é justamente desenvolver software, ele pertence ao **empregador ou contratante**, salvo acordo em contrário.
- Se foi desenvolvido sem relação com o contrato e **sem usar recursos, equipamentos ou informações** do empregador, ele pertence a quem desenvolveu.

**[COMPLETAR: isso muda algo na forma como você fecha contratos na IronFrame, ou em projetos paralelos feitos fora do horário de trabalho?]**

## Certificados e assinaturas digitais — MP nº 2.200-2/2001 e Lei nº 14.063/2020

A Medida Provisória 2.200-2 criou a **ICP-Brasil**, a infraestrutura de chaves públicas brasileira. Documentos assinados com um certificado ICP-Brasil têm presunção de veracidade, como uma assinatura reconhecida em cartório.

A Lei nº 14.063/2020 organizou as assinaturas eletrônicas em três níveis para interações com o poder público:

- **Simples:** identifica quem assinou (login e senha, por exemplo).
- **Avançada:** vincula a assinatura ao signatário de forma inequívoca, sem precisar de certificado ICP-Brasil (é o caso da conta gov.br nível prata/ouro).
- **Qualificada:** usa certificado ICP-Brasil e é a de maior validade jurídica.

**Na prática, para quem é de TI:** quem desenvolve sistemas que lidam com contratos, documentos oficiais ou integração com órgãos públicos precisa saber qual nível de assinatura cada operação exige. É aqui que criptografia assimétrica sai da sala de aula e vira requisito de produto.

## Lei de Acesso à Informação — Lei nº 12.527/2011

É a lei que garante a qualquer pessoa o direito de pedir informações a órgãos públicos, sem precisar justificar o motivo. A regra é a **transparência**; o sigilo é a exceção. Quando há sigilo, a informação pode ser classificada como reservada (até 5 anos), secreta (até 15 anos) ou ultrassecreta (até 25 anos).

**Na prática, para quem é de TI:** o artigo 8º obriga os órgãos públicos a manter sites com transparência ativa, e lista requisitos técnicos bem concretos: ferramenta de busca, exportação em **formatos abertos e não proprietários**, acesso automatizado por sistemas externos em formatos **legíveis por máquina** e acessibilidade para pessoas com deficiência. Quem desenvolve portais de transparência ou APIs de dados abertos está, na prática, implementando a LAI.

## Lei Carolina Dieckmann — Lei nº 12.737/2012

É a lei que tipifica o crime de invasão de dispositivos. Ela incluiu o artigo 154-A no Código Penal e ganhou esse apelido depois que fotos íntimas da atriz foram vazadas a partir de uma invasão ao seu computador.

Em 2021, a **Lei nº 14.155** endureceu as penas (que passaram a ser de 1 a 4 anos de reclusão) e retirou a exigência de que a invasão ocorresse "mediante violação de mecanismo de segurança" — ou seja, acessar um dispositivo desprotegido sem autorização também é crime. A mesma lei criou os crimes de **fraude eletrônica** e **furto mediante fraude eletrônica**, com penas de 4 a 8 anos, voltados a golpes como phishing e clonagem de WhatsApp.

**Na prática, para quem é de TI:** a palavra que separa um teste de segurança de um crime é **autorização**. Pentest, varredura de vulnerabilidades ou "só dar uma olhada" num sistema de terceiros precisam de autorização expressa e, de preferência, por escrito, com escopo definido. A lei também pune quem produz ou distribui programas feitos para permitir a invasão.

## Marco Civil da Internet — Lei nº 12.965/2014

Determina os direitos e deveres ao se utilizar a internet no Brasil. É considerada a "constituição da internet" brasileira e se apoia em três pilares: neutralidade de rede, privacidade e liberdade de expressão.

**Na prática, para quem é de TI:**

- **Neutralidade de rede:** o provedor de conexão não pode tratar pacotes de forma diferente de acordo com o conteúdo, a origem ou o destino — não pode, por exemplo, deixar um serviço de streaming mais lento para favorecer o seu próprio.
- **Guarda de registros (logs):** o provedor de conexão deve guardar os registros de conexão por **1 ano**; o provedor de aplicação (sites e apps mantidos por empresas) deve guardar os registros de acesso à aplicação por **6 meses**. Esses dados só podem ser entregues a terceiros com ordem judicial. Isso afeta diretamente política de retenção de logs e arquitetura de observabilidade.
- **Responsabilidade por conteúdo de terceiros (art. 19):** pelo texto original, uma plataforma só respondia por conteúdo publicado por usuários se descumprisse uma ordem judicial de remoção. Em 2025, o STF considerou esse artigo parcialmente inconstitucional: para boa parte dos conteúdos ilícitos, a plataforma pode ser responsabilizada se não agir após uma notificação extrajudicial, e a exigência de ordem judicial ficou restrita principalmente a crimes contra a honra. **[CONFERIR: detalhes da tese fixada pelo STF antes de publicar.]**

**[COMPLETAR: aqui cabe a sua opinião sobre a decisão do STF — é um dos temas "polêmicos" que você citou na introdução.]**

## Lei Geral de Proteção de Dados — Lei nº 13.709/2018

A famosa LGPD surge para tratar dos dados pessoais de qualquer pessoa natural — não apenas de cidadãos brasileiros, mas de qualquer pessoa cujos dados sejam tratados no Brasil. Ela busca garantir direitos fundamentais de liberdade e privacidade. Em resumo, a LGPD serve para proteger os dados pessoais das pessoas de serem mal usados por empresas e governo.

### Órgãos criados pela LGPD

**Autoridade Nacional de Proteção de Dados (ANPD):** É a agência reguladora brasileira responsável por fiscalizar se a LGPD está sendo cumprida. Ela tem autonomia para investigar possíveis violadores da lei e, em caso de descumprimento, puni-los.

**Conselho Nacional de Proteção de Dados (CNPD):** É composto por servidores públicos de diversos órgãos e membros da sociedade civil. O CNPD participa da formulação de diretrizes e estudos relacionados à proteção de dados, mas não toma a decisão final (por isso se chama conselho).

### Quem é quem na LGPD

Notícias sobre a LGPD sempre vão se referir aos envolvidos da seguinte forma (pela lei, apenas o controlador e o operador são chamados de *agentes de tratamento*):

| Papel | O que é                                                                                             | Palavra-chave | Exemplo prático                                                                                     |
| ----------------- | ------------------------------------------------------------------------------------------------------------ | ------------- | --------------------------------------------------------------------------------------------------- |
| **Titular**       | Pessoa natural a quem os dados pessoais se referem                                                           | **Pessoa**    | Cidadão fornece nome, CPF e e-mail para uma empresa                                                 |
| **Controlador**   | Pessoa natural ou jurídica que **toma as decisões referentes ao tratamento** dos dados                       | **Decide**    | A empresa decide coletar o CPF dos clientes para emitir notas fiscais                               |
| **Operador**      | Pessoa natural ou jurídica que **realiza o tratamento em nome do controlador**                               | **Executa**   | Um serviço de cloud armazena/processa os dados da empresa conforme suas instruções                  |
| **Encarregado**   | Atua como **canal de comunicação** entre controlador, titulares e ANPD e exerce as demais atribuições legais | **Comunica**  | O encarregado recebe uma solicitação de titular sobre seus dados e faz a interlocução com a empresa |

### Um exemplo completo para fixar

Imagine que uma empresa pública contrate uma empresa de TI para armazenar dados de cidadãos. Nesse caso temos:

**Cidadão** → Titular

**Empresa pública**, que determina a finalidade e como os dados serão tratados → Controlador

**Empresa de TI**, que processa/armazena os dados em nome da empresa pública → Operador

**Encarregado da empresa pública** → canal entre titulares, controlador e ANPD

**ANPD** → fiscaliza a aplicação da LGPD

**CNPD** → órgão consultivo relacionado à proteção de dados

### O que a LGPD muda no dia a dia de quem desenvolve

**Toda coleta precisa de uma base legal.** O artigo 7º lista dez hipóteses que autorizam o tratamento de dados pessoais. Consentimento é só uma delas — e muitas vezes não é a mais adequada. As que mais aparecem no dia a dia são:

- **Consentimento** do titular, que precisa ser livre, informado e pode ser revogado a qualquer momento;
- **Execução de contrato** (o endereço de entrega numa compra, por exemplo);
- **Cumprimento de obrigação legal** (como emitir nota fiscal);
- **Legítimo interesse** do controlador, desde que não se sobreponha aos direitos do titular.

**Dados sensíveis têm regras mais rígidas.** Dados de saúde, biometria, genética, origem racial, religião, opinião política e vida sexual são considerados *sensíveis* e têm um conjunto mais restrito de bases legais — o legítimo interesse, por exemplo, não vale para eles.

**[COMPLETAR: o seu TCC coletava BPM, SpO2 e temperatura corporal — dados de saúde, portanto sensíveis — e gerava relatórios usando a API do Gemini. Vale contar aqui: qual seria a base legal? Você sabia disso na época? O que faria diferente num produto real? Repare que, ao enviar os dados para a API, o Google passa a atuar como operador, e o tratamento pode envolver transferência internacional de dados (art. 33).]**

**O titular tem direitos que o sistema precisa suportar.** O artigo 18 garante ao titular, entre outros, o direito de confirmar se seus dados são tratados, acessá-los, corrigi-los, pedir a eliminação e a portabilidade. Isso significa que alguém, em algum momento, vai precisar responder "quais dados temos sobre essa pessoa?" — e o banco de dados precisa ter sido modelado para que essa pergunta tenha resposta.

**Decisões automatizadas podem ser revistas.** O artigo 20 garante ao titular o direito de pedir revisão de decisões tomadas unicamente com base em tratamento automatizado — como uma análise de crédito feita por um modelo. Com a popularização da IA, esse artigo tende a ganhar cada vez mais importância.

**Segurança desde a concepção.** O artigo 46 exige medidas técnicas para proteger os dados e diz que elas devem ser pensadas **desde a fase de concepção** do produto. Criptografia, controle de acesso, minimização (coletar só o necessário) e anonimização deixam de ser boas práticas e passam a ser obrigação. Vale lembrar: dado **anonimizado** de forma irreversível deixa de ser dado pessoal; dado **pseudonimizado** (com um ID no lugar do nome, mas que ainda pode ser revertido) continua sendo.

**Incidentes precisam ser comunicados.** Em caso de vazamento que possa gerar risco ou dano relevante, o controlador precisa comunicar a ANPD e os titulares afetados. A regulamentação da ANPD fixou o prazo em **3 dias úteis**. Para isso, é preciso ter logs e monitoramento capazes de detectar o incidente e dizer o que foi exposto.

**As sanções são pesadas.** Vão de advertência a multa de até **2% do faturamento** da empresa no Brasil, limitada a **R$ 50 milhões por infração**, além de publicização da infração, bloqueio ou eliminação dos dados e suspensão do banco de dados ou da atividade de tratamento.

## Marco Legal das Startups — Lei Complementar nº 182/2021

Define o que é uma startup (receita bruta de até R$ 16 milhões no ano anterior e até 10 anos de CNPJ, entre outros critérios) e cria instrumentos para facilitar a inovação:

- O **investidor-anjo** não é considerado sócio e não responde por dívidas da empresa, o que reduz o risco de investir;
- **Sandbox regulatório:** órgãos reguladores podem suspender temporariamente certas exigências para que startups testem modelos inovadores;
- Uma modalidade especial de **licitação** para que o poder público contrate soluções inovadoras de startups.

**[COMPLETAR: como isso se conecta com a IronFrame ou com seus planos de empreender?]**

## ECA Digital — Lei nº 15.211/2025

Também chamada de Estatuto Digital da Criança e do Adolescente, foi sancionada em setembro de 2025 e se aplica a produtos e serviços digitais direcionados a crianças e adolescentes ou de acesso provável por eles. **[CONFERIR: data de entrada em vigor e regulamentação.]**

**Na prática, para quem é de TI:**

- **Verificação de idade** confiável — a simples autodeclaração ("tenho mais de 18 anos") deixa de ser suficiente;
- Configurações **mais protetivas por padrão** para menores;
- Ferramentas de **supervisão parental**;
- Proibição de **loot boxes** (caixas de recompensa aleatória) em jogos acessados por crianças e adolescentes;
- Contas de menores de 16 anos em redes sociais vinculadas à conta de um responsável.

É uma lei que mexe diretamente em fluxo de cadastro, autenticação e design de produto.

## Marco Legal da Inteligência Artificial — PL nº 2.338/2023 (em tramitação)

Ainda não é lei, mas está no horizonte. O projeto foi aprovado pelo Senado em dezembro de 2024 e seguiu para a Câmara dos Deputados. **[CONFERIR: situação atual da tramitação.]**

A proposta segue a linha do AI Act europeu e classifica sistemas de IA por **nível de risco**: alguns usos seriam proibidos (risco excessivo) e sistemas de alto risco — como os usados em recrutamento, crédito ou saúde — teriam obrigações de transparência, avaliação de impacto e supervisão humana.

**[COMPLETAR: sua visão sobre regulação de IA, considerando que você usa IA generativa no dia a dia (como conta na página Sobre).]**

## O que levo disso

**[COMPLETAR: conclusão. Algumas perguntas que podem ajudar: o que mais te surpreendeu? Qual lei você acha que tem mais impacto no seu trabalho hoje? O que muda na forma como você vai projetar o próximo sistema?]**
