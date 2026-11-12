---
draft: false
title: "Legislações relevantes para a minha área de TI"
description: "Quais são as leis que um bom engenheiro da computação deve dominar?"
date: 2026-11-11
categoria: "reflexoes"
tags: ["Legislação", "Leis", "LGPD"]
---

Recentemente conversei com algumas pessoas e cheguei à conclusão que estava na hora de dominar quais leis brasileiras são relevantes para um profissional de TI. Vemos cada vez mais notícias e polêmicas a respeito do mundo da tecnologia e eu sinto que tenho a obrigação de entender o que está acontecendo para ajudar as pessoas e para executar o meu trabalho sempre dentro das regras.

Não sou advogado, e este texto não é aconselhamento jurídico. É o registro do que entendi até agora, olhando pela lente de quem projeta, desenvolve e opera sistemas.

Em ordem cronológica, as leis brasileiras relevantes para a TI são:

## Código de Defesa do Consumidor — [Lei nº 8.078/1990](https://www.planalto.gov.br/ccivil_03/leis/l8078compilado.htm)

É anterior à internet comercial no Brasil, mas vale para qualquer sistema que venda algo a um consumidor final. Em 2013, o [Decreto nº 7.962](https://www.planalto.gov.br/ccivil_03/_ato2011-2014/2013/decreto/d7962.htm) regulamentou o CDC para o comércio eletrônico.

**Na prática, para quem é de TI:** um e-commerce precisa exibir de forma clara a identificação da empresa (razão social, CNPJ, endereço), o preço total com frete e as condições da oferta, além de permitir o **direito de arrependimento** — o cliente pode desistir de uma compra feita pela internet em até 7 dias, e o sistema precisa oferecer um caminho para isso.

## Lei do Software — [Lei nº 9.609/1998](https://www.planalto.gov.br/ccivil_03/leis/l9609.htm)

Programa de computador é protegido como obra intelectual, pelo regime de direito autoral (a [Lei nº 9.610/1998](https://www.planalto.gov.br/ccivil_03/leis/l9610.htm), de Direitos Autorais, se aplica de forma complementar). A proteção dura 50 anos e não depende de registro — registrar no INPI é opcional, mas ajuda a provar a autoria.

**Na prática, para quem é de TI:** a pergunta mais importante que essa lei responde é *de quem é o código que eu escrevo?*

- Se o software foi desenvolvido durante um contrato de trabalho ou de prestação de serviço cujo objeto é justamente desenvolver software, ele pertence ao **empregador ou contratante**, salvo acordo em contrário.
- Se foi desenvolvido sem relação com o contrato e **sem usar recursos, equipamentos ou informações** do empregador, ele pertence a quem desenvolveu.

## Certificados e assinaturas digitais — [MP nº 2.200-2/2001](https://www.planalto.gov.br/ccivil_03/mpv/antigas_2001/2200-2.htm) e [Lei nº 14.063/2020](https://www.planalto.gov.br/ccivil_03/_ato2019-2022/2020/lei/l14063.htm)

A Medida Provisória 2.200-2 criou a **ICP-Brasil**, a infraestrutura de chaves públicas brasileira. Documentos assinados com um certificado ICP-Brasil têm presunção de veracidade, como uma assinatura reconhecida em cartório.

A Lei nº 14.063/2020 organizou as assinaturas eletrônicas em três níveis para interações com o poder público:

- **Simples:** identifica quem assinou (login e senha, por exemplo).
- **Avançada:** vincula a assinatura ao signatário de forma inequívoca, sem precisar de certificado ICP-Brasil (é o caso da conta gov.br nível prata/ouro).
- **Qualificada:** usa certificado ICP-Brasil e é a de maior validade jurídica.

**Na prática, para quem é de TI:** quem desenvolve sistemas que lidam com contratos, documentos oficiais ou integração com órgãos públicos precisa saber qual nível de assinatura cada operação exige. É aqui que criptografia assimétrica sai da sala de aula e vira requisito de produto.

## Lei de Acesso à Informação — [Lei nº 12.527/2011](https://www.planalto.gov.br/ccivil_03/_ato2011-2014/2011/lei/l12527.htm)

É a lei que garante a qualquer pessoa o direito de pedir informações a órgãos públicos, sem precisar justificar o motivo. A regra é a **transparência**; o sigilo é a exceção. Quando há sigilo, a informação pode ser classificada como reservada (até 5 anos), secreta (até 15 anos) ou ultrassecreta (até 25 anos).

**Na prática, para quem é de TI:** o artigo 8º obriga os órgãos públicos a manter sites com transparência ativa, e lista requisitos técnicos bem concretos: ferramenta de busca, exportação em **formatos abertos e não proprietários**, acesso automatizado por sistemas externos em formatos **legíveis por máquina** e acessibilidade para pessoas com deficiência. Quem desenvolve portais de transparência ou APIs de dados abertos está, na prática, implementando a LAI.

## Lei Carolina Dieckmann — [Lei nº 12.737/2012](https://www.planalto.gov.br/ccivil_03/_ato2011-2014/2012/lei/l12737.htm)

É a lei que tipifica o crime de invasão de dispositivos. Ela incluiu o artigo 154-A no Código Penal e ganhou esse apelido depois que fotos íntimas da atriz foram vazadas a partir de uma invasão ao seu computador.

Em 2021, a **[Lei nº 14.155](https://www.planalto.gov.br/ccivil_03/_ato2019-2022/2021/lei/l14155.htm)** endureceu as penas (que passaram a ser de 1 a 4 anos de reclusão) e retirou a exigência de que a invasão ocorresse "mediante violação de mecanismo de segurança" — ou seja, acessar um dispositivo desprotegido sem autorização também é crime. A mesma lei criou os crimes de **fraude eletrônica** e **furto mediante fraude eletrônica**, com penas de 4 a 8 anos, voltados a golpes como phishing e clonagem de WhatsApp.

**Na prática, para quem é de TI:** a palavra que separa um teste de segurança de um crime é **autorização**. Pentest, varredura de vulnerabilidades ou "só dar uma olhada" num sistema de terceiros precisam de autorização expressa e, de preferência, por escrito, com escopo definido. A lei também pune quem produz ou distribui programas feitos para permitir a invasão.

## Marco Civil da Internet — [Lei nº 12.965/2014](https://www.planalto.gov.br/ccivil_03/_ato2011-2014/2014/lei/l12965.htm)

Determina os direitos e deveres ao se utilizar a internet no Brasil. É considerada a "constituição da internet" brasileira e se apoia em três pilares: neutralidade de rede, privacidade e liberdade de expressão.

**Na prática, para quem é de TI:**

- **Neutralidade de rede:** o provedor de conexão não pode tratar pacotes de forma diferente de acordo com o conteúdo, a origem ou o destino — não pode, por exemplo, deixar um serviço de streaming mais lento para favorecer o seu próprio.
- **Guarda de registros (logs):** o provedor de conexão deve guardar os registros de conexão por **1 ano**; o provedor de aplicação (sites e apps mantidos por empresas) deve guardar os registros de acesso à aplicação por **6 meses**. Esses registros só podem ser entregues a terceiros com ordem judicial. A exceção são os dados cadastrais (qualificação pessoal, filiação e endereço), que autoridades administrativas com competência legal, como a polícia e o Ministério Público, podem requisitar sem ordem judicial (art. 10, §3º). Isso afeta diretamente política de retenção de logs e arquitetura de observabilidade.
- **Responsabilidade por conteúdo de terceiros (art. 19):** pelo texto original, uma plataforma só respondia por conteúdo publicado por usuários se descumprisse uma ordem judicial de remoção. Em junho de 2025, ao julgar os [Temas 987](https://portal.stf.jus.br/jurisprudenciaRepercussao/tema.asp?num=987) e 533, o STF considerou esse artigo parcialmente inconstitucional, por 8 votos a 3. Pela tese fixada:
  - **Regra geral:** a plataforma pode ser responsabilizada se não remover um conteúdo ilícito depois de ser notificada pelo próprio ofendido, sem precisar de ordem judicial (o regime do art. 21).
  - **Crimes contra a honra:** continua valendo o art. 19 original, ou seja, a responsabilização só ocorre se a plataforma descumprir uma ordem judicial.
  - **Conteúdos graves:** para terrorismo, tentativa de golpe de Estado, racismo, homofobia, instigação ao suicídio ou à automutilação e crimes contra mulheres e crianças, a plataforma tem um **dever de cuidado** e responde se houver falha sistêmica em impedir ou remover esse tipo de conteúdo, mesmo sem notificação.
  - **Anúncios e impulsionamento:** em conteúdo pago ou distribuído por robôs, a responsabilidade da plataforma é presumida.
  - **Mensagens privadas e e-mail:** ficam fora do novo regime e continuam sob o art. 19.

  Em junho de 2026, o STF julgou os embargos contra essa decisão. O núcleo da tese foi mantido, e as plataformas ganharam 60 dias para se adaptar.

## Lei Geral de Proteção de Dados — [Lei nº 13.709/2018](https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709compilado.htm)

A famosa LGPD surge para tratar dos dados pessoais de qualquer pessoa natural — não apenas de cidadãos brasileiros, mas de qualquer pessoa cujos dados sejam tratados no Brasil. Ela busca garantir direitos fundamentais de liberdade e privacidade. Em resumo, a LGPD serve para proteger os dados pessoais das pessoas de serem mal usados por empresas e governo.

### Órgãos criados pela LGPD

**Agência Nacional de Proteção de Dados (ANPD):** É a agência reguladora brasileira responsável por fiscalizar se a LGPD está sendo cumprida. Até pouco tempo atrás se chamava *Autoridade* Nacional de Proteção de Dados, e hoje também fiscaliza o ECA Digital. Ela tem autonomia para investigar possíveis violadores da lei e, em caso de descumprimento, puni-los.

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

**O titular tem direitos que o sistema precisa suportar.** O artigo 18 garante ao titular, entre outros, o direito de confirmar se seus dados são tratados, acessá-los, corrigi-los, pedir a eliminação e a portabilidade. Isso significa que alguém, em algum momento, vai precisar responder "quais dados temos sobre essa pessoa?" — e o banco de dados precisa ter sido modelado para que essa pergunta tenha resposta.

**Decisões automatizadas podem ser revistas.** O artigo 20 garante ao titular o direito de pedir revisão de decisões tomadas unicamente com base em tratamento automatizado — como uma análise de crédito feita por um modelo. Com a popularização da IA, esse artigo tende a ganhar cada vez mais importância.

**Segurança desde a concepção.** O artigo 46 exige medidas técnicas para proteger os dados e diz que elas devem ser pensadas **desde a fase de concepção** do produto. Criptografia, controle de acesso, minimização (coletar só o necessário) e anonimização deixam de ser boas práticas e passam a ser obrigação. Vale lembrar: dado **anonimizado** de forma irreversível deixa de ser dado pessoal; dado **pseudonimizado** (com um ID no lugar do nome, mas que ainda pode ser revertido) continua sendo.

**Incidentes precisam ser comunicados.** Em caso de vazamento que possa gerar risco ou dano relevante, o controlador precisa comunicar a ANPD e os titulares afetados. A regulamentação da ANPD fixou o prazo em **3 dias úteis**. Para isso, é preciso ter logs e monitoramento capazes de detectar o incidente e dizer o que foi exposto.

**As sanções são pesadas.** Vão de advertência a multa de até **2% do faturamento** da empresa no Brasil, limitada a **R$ 50 milhões por infração**, além de publicização da infração, bloqueio ou eliminação dos dados e suspensão do banco de dados ou da atividade de tratamento.

**Revisitando o meu TCC com a LGPD em mãos.** No meu [Trabalho de Conclusão de Curso](/projetos/tcc-monitor-sinais-vitais/), construí um sistema que mede BPM, SpO2 e temperatura corporal com sensores ligados a um ESP32, envia as leituras por Wi-Fi para um servidor Flask, guarda tudo em um banco MySQL e usa a API do Gemini para gerar relatórios. Como projeto acadêmico, ele funcionou bem. Mas, relendo a arquitetura depois de estudar a lei, percebi que cada camada tem uma implicação jurídica:

- **Os dados são sensíveis.** BPM, SpO2 e temperatura são dados referentes à saúde. Num produto real, o legítimo interesse não serviria como base legal. As opções seriam o **consentimento específico e destacado**, para finalidades bem definidas (art. 11, I), ou a **tutela da saúde**, que só vale quando o tratamento é feito por profissionais ou serviços de saúde (art. 11, II, f). Como a ideia era um médico acompanhar o paciente a distância, a segunda faria sentido se o produto fosse oferecido por uma clínica. Se fosse vendido direto ao usuário, restaria o consentimento.
- **O Gemini vira um agente de tratamento.** Ao enviar as leituras para a API, o Google passa a tratar dados de saúde em nome de quem opera o sistema, ou seja, passa a atuar como **operador**. Como os servidores ficam fora do Brasil, isso também é **transferência internacional de dados** (art. 33). Antes de colocar algo assim em produção, eu precisaria ler os termos da API para saber se os dados enviados podem ser usados para treinar modelos (isso costuma variar entre o plano gratuito e o pago) e onde eles ficam armazenados.
- **Minimizar o que sai do servidor.** A IA não precisa saber *quem* é o paciente para interpretar uma série de leituras. Mandar só os números, sem nome, e-mail ou qualquer identificador, já reduz bastante o risco. Mesmo assim, como vimos acima, dado pseudonimizado continua sendo dado pessoal, e as obrigações não desaparecem.
- **"Diagnóstico" gerado por IA é decisão automatizada.** Um relatório que sugere que algo está errado com a saúde de alguém se encaixa no espírito do art. 20: a pessoa tem direito de pedir revisão. O aviso de que o sistema não substitui um médico, que eu já colocava no projeto, deixaria de ser só um cuidado e passaria a ser parte do desenho do produto, com um profissional de saúde no meio do caminho.
- **Algumas escolhas já iam na direção certa.** O dashboard exigia login e senha, e o histórico ficava limitado às últimas 24 horas, o que é minimização na prática. Num produto real, eu somaria a isso criptografia no tráfego entre o ESP32 e o servidor, criptografia no banco e uma forma de o usuário exportar ou apagar os próprios dados (art. 18).

A lição que tiro é que a LGPD não é um documento que o jurídico anexa no fim do projeto. Ela muda decisões de arquitetura: o que coletar, para onde enviar, por quanto tempo guardar e quem pode ver.

## Marco Legal das Startups — [Lei Complementar nº 182/2021](https://www.planalto.gov.br/ccivil_03/leis/lcp/lcp182.htm)

Define o que é uma startup (receita bruta de até R$ 16 milhões no ano anterior e até 10 anos de CNPJ, entre outros critérios) e cria instrumentos para facilitar a inovação:

- O **investidor-anjo** não é considerado sócio e não responde por dívidas da empresa, o que reduz o risco de investir;
- **Sandbox regulatório:** órgãos reguladores podem suspender temporariamente certas exigências para que startups testem modelos inovadores;
- Uma modalidade especial de **licitação** para que o poder público contrate soluções inovadoras de startups.

## ECA Digital — [Lei nº 15.211/2025](https://www.planalto.gov.br/ccivil_03/_ato2023-2026/2025/lei/L15211.htm)

Também chamada de Estatuto Digital da Criança e do Adolescente, foi sancionada em setembro de 2025 e se aplica a produtos e serviços digitais direcionados a crianças e adolescentes ou de acesso provável por eles. Está **em vigor desde 17 de março de 2026** e foi regulamentada pelo [Decreto nº 12.880/2026](https://www.planalto.gov.br/ccivil_03/_ato2023-2026/2026/decreto/D12880.htm). A fiscalização cabe à ANPD, que ainda está editando as normas complementares, como os padrões técnicos de verificação de idade e de supervisão parental.

**Na prática, para quem é de TI:**

- **Verificação de idade** confiável — a simples autodeclaração ("tenho mais de 18 anos") deixa de ser suficiente;
- Configurações **mais protetivas por padrão** para menores;
- Ferramentas de **supervisão parental**;
- Proibição de **loot boxes** (caixas de recompensa aleatória) em jogos acessados por crianças e adolescentes;
- Contas de menores de 16 anos em redes sociais vinculadas à conta de um responsável.

É uma lei que mexe diretamente em fluxo de cadastro, autenticação e design de produto.

## Marco Legal da Inteligência Artificial — [PL nº 2.338/2023](https://www.camara.leg.br/proposicoesWeb/fichadetramitacao?idProposicao=2487262) (em tramitação)

Ainda não é lei, mas está no horizonte. O projeto foi aprovado pelo Senado em dezembro de 2024 e seguiu para a Câmara dos Deputados, onde está desde então em uma comissão especial, aguardando o parecer do relator. A votação, prevista para maio de 2026, foi adiada para depois das eleições de outubro. Se a Câmara alterar o texto, ele ainda volta ao Senado antes de ir à sanção.

A proposta segue a linha do AI Act europeu e classifica sistemas de IA por **nível de risco**: alguns usos seriam proibidos (risco excessivo) e sistemas de alto risco — como os usados em recrutamento, crédito ou saúde — teriam obrigações de transparência, avaliação de impacto e supervisão humana.

Essa é uma discussão importante, porém muito nova, e desconfio de quem fala sobre ela com certeza absoluta. Ainda assim, entendo que algum grau de regulação é necessário, como o combate frontal a qualquer tipo de deepfake que faça mal à imagem ou à honra de uma pessoa. Imagino que com isso todos concordem; tanto que o TSE já proibiu deepfakes na propaganda eleitoral em 2024.

O desafio real está em apontar onde a linha deve ser traçada. Até onde o cidadão deve ter a liberdade de usar as tecnologias da forma que deseja? Até onde o Estado deve monitorar e regular como alguém usa uma tecnologia? O PL 2.338 tenta responder isso regulando os sistemas pelo risco que oferecem, e não as pessoas que os usam. Olhando para o meu próprio TCC, faz sentido para mim: um sistema que gera relatórios sobre a saúde de alguém não pode ser tratado da mesma forma que um assistente que me ajuda a revisar um texto. Ainda são perguntas sem resposta definitiva, mas experiências passadas, como a das redes sociais, cuja responsabilidade acabou sendo decidida pelo STF, nos mostram que o mau uso de uma nova tecnologia pode ser extremamente destrutivo.

Outro debate ainda mais complexo é se os Estados devem, de alguma forma, frear o avanço da construção de inteligências artificiais. Mas vou deixar esse debate para outro dia.

## O que levo disso

Algo que devo confessar é que eu imaginava que as leis relevantes para a área de TI eram apenas quatro: a Lei de Acesso à Informação, a Lei Carolina Dieckmann, o Marco Civil e a LGPD. Foi interessante entender como as demais, do CDC à Lei do Software, funcionam e interferem na nossa área. A maior mudança para mim é passar a enxergar a lei como requisito de projeto, tão importante quanto desempenho ou segurança, e não como algo para pensar depois que o sistema está pronto.

Em meio a tantas polêmicas, é importante estudar e entender por conta própria o que está acontecendo.
