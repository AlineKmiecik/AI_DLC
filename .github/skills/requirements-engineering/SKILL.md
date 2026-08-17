---

name: requirements-engineering
description: Metodologia para consolidar múltiplas análises de reuniões e documentos, identificar lacunas, produzir perguntas priorizadas, registrar respostas, formalizar requisitos, histórias de usuário e critérios de aceite com rastreabilidade. Use ao criar, revisar, complementar ou validar o dossiê de requisitos de uma demanda.
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Objetivo

Transformar fontes distribuídas em um dossiê único, consistente,
rastreável e adequado para as etapas seguintes do AI-DLC.

A skill deve suportar contexto acumulado ao longo do tempo.

Uma demanda pode possuir:

* várias reuniões;
* documentos de negócio;
* decisões posteriores;
* protótipos;
* imagens;
* regras existentes;
* respostas de diferentes equipes;
* versões sucessivas de requisitos.

# Artefato obrigatório

Utilize o template:

`requirements-analysis-template.md`

Produza ou atualize:

`docs/ai-dlc/work-items/<work-item-id>/requirements-analysis.md`

Quando o usuário indicar outro caminho, utilize o caminho informado.

Mantenha todos os títulos definidos no template.

Quando uma seção tiver sido analisada e não possuir conteúdo, utilize:

`Nenhum item identificado.`

Isso diferencia uma seção vazia de uma seção esquecida.

# Princípio central

Não busque apenas gerar um documento completo.

Busque produzir um documento:

* correto;
* verificável;
* rastreável;
* explicitamente incompleto quando faltarem informações.

Uma pergunta clara é melhor do que um requisito inventado.

# Processo geral

## Passo 1 — Identificar a demanda

Determine:

* identificador;
* título;
* problema ou oportunidade;
* projeto ou sistema relacionado;
* diretório de saída;
* pessoas ou equipes envolvidas.

Quando não houver identificador, utilize `work-item-draft`.

## Passo 2 — Inventariar as fontes

Registre todas as fontes antes de consolidar conclusões.

Para cada fonte, registre:

* identificador;
* caminho ou nome;
* tipo;
* status;
* autoridade;
* data, quando disponível;
* escopo coberto;
* observações.

Tipos possíveis:

* `meeting-analysis`
* `business-document`
* `policy`
* `existing-requirement`
* `system-documentation`
* `process-flow`
* `prototype`
* `image`
* `user-answer`
* `user-correction`
* `unvalidated-source`

Status possíveis:

* `validated`
* `official`
* `reference`
* `draft`
* `unvalidated`
* `superseded`

Não trate `draft` ou `unvalidated` como confirmação definitiva.

## Passo 3 — Consolidar o contexto

Extraia e normalize:

* problema;
* objetivo;
* resultado de negócio esperado;
* atores;
* sistemas;
* processos;
* necessidades;
* decisões;
* restrições;
* regras;
* dados;
* integrações;
* erros;
* exceções;
* itens fora do escopo;
* ações pendentes.

Quando a mesma informação aparecer em várias fontes:

1. consolide-a em um único item;
2. preserve todas as referências;
3. aumente a confiança somente quando as fontes forem compatíveis;
4. não crie requisitos duplicados.

## Passo 4 — Construir o glossário

Identifique:

* termos de negócio;
* siglas;
* nomes de sistemas;
* nomes diferentes para o mesmo conceito;
* termos potencialmente ambíguos.

Quando dois termos parecerem equivalentes, não os unifique
silenciosamente. Crie uma pergunta quando a equivalência puder alterar
o entendimento.

## Passo 5 — Identificar conflitos

Compare as fontes procurando:

* regras incompatíveis;
* valores diferentes;
* nomes conflitantes;
* fluxos divergentes;
* mudanças de escopo;
* responsabilidades incompatíveis;
* versões diferentes de um mesmo comportamento.

Para cada conflito, crie:

* identificador `CNF-###`;
* descrição;
* fontes envolvidas;
* impacto;
* requisitos afetados;
* pergunta necessária para resolução;
* status.

Não utilize automaticamente a fonte mais recente como vencedora.

## Passo 6 — Identificar lacunas

Avalie a cobertura das seguintes dimensões.

### Objetivo e sucesso

* Qual problema será resolvido?
* Qual resultado representa sucesso?
* Como o resultado será verificado?
* Existe métrica de negócio?

### Escopo

* O que está incluído?
* O que está explicitamente excluído?
* Existem fases ou entregas parciais?
* Existe comportamento atual que deve ser preservado?

### Atores e acesso

* Quem executa a operação?
* Quem visualiza o resultado?
* Existem perfis ou permissões?
* Existem diferenças por empresa, área ou usuário?

### Fluxo principal

* Qual evento inicia o fluxo?
* Quais passos são observáveis?
* Qual resultado final é esperado?
* Existe confirmação ou retorno ao usuário?

### Regras de negócio

* Quais condições alteram o resultado?
* Existem limites?
* Existem cálculos?
* Existem datas de referência?
* Existem exceções?
* Existem prioridades entre regras?

### Dados

* Quais dados são obrigatórios?
* Qual é a origem?
* Quais validações existem?
* Como tratar ausência, duplicidade ou inconsistência?
* Existem dados sensíveis?

### Integrações

* Quais sistemas participam?
* Qual sistema inicia a comunicação?
* Quais informações são trocadas?
* O que acontece em caso de indisponibilidade?
* Existe reprocessamento ou idempotência como necessidade de negócio?

### Erros e exceções

* Quais erros precisam ser informados?
* Qual comportamento é esperado após uma falha?
* O usuário pode tentar novamente?
* Existe processamento parcial?

### Requisitos não funcionais

* Existe expectativa de desempenho?
* Existe volume conhecido?
* Existe necessidade de auditoria?
* Existe requisito de segurança?
* Existe requisito de disponibilidade?
* Existe restrição regulatória?
* Existe requisito de acessibilidade?

### Aceitação

* Como cada requisito será verificado?
* Existem cenários positivos e negativos?
* Os resultados são observáveis?
* Existe informação suficiente para testar?

Não crie uma pergunta para toda lacuna teórica. Crie perguntas somente
quando forem relevantes ao escopo da demanda.

## Passo 7 — Criar perguntas

Antes de adicionar uma pergunta:

1. busque a resposta em todas as fontes;
2. verifique o registro de perguntas;
3. verifique respostas anteriores;
4. determine o impacto;
5. determine a prioridade;
6. determine se ela bloqueia a próxima etapa.

Uma pergunta deve ser:

* específica;
* neutra;
* atômica;
* respondível;
* contextualizada;
* ligada a itens afetados.

Evite perguntas compostas.

Evite:

`Como deve funcionar o fluxo e quais erros devem ser exibidos?`

Prefira:

`QST-004 — Quando a integração estiver indisponível, a operação deve ser
rejeitada imediatamente ou permanecer pendente para reprocessamento?`

E separadamente:

`QST-005 — Qual mensagem deve ser apresentada ao usuário quando a
integração estiver indisponível?`

## Passo 8 — Priorizar perguntas

Classifique:

### P0 — Bloqueante

Sem a resposta, não é possível definir corretamente:

* comportamento principal;
* escopo;
* regra crítica;
* segurança;
* contrato essencial;
* critério de aceite principal.

### P1 — Alto impacto

A resposta pode alterar significativamente:

* uma história;
* integração;
* regra;
* permissão;
* exceção;
* requisito não funcional.

### P2 — Importante

A resposta melhora precisão ou testabilidade, mas não impede a
formalização inicial.

### P3 — Posterior

A pergunta pode ser tratada como melhoria, decisão futura ou detalhe
não essencial.

Apresente no chat no máximo dez perguntas por rodada.

Ordene por:

1. bloqueio;
2. impacto;
3. dependência;
4. quantidade de itens afetados.

## Passo 9 — Registrar respostas

Nunca substitua a pergunta pela resposta.

Preserve:

* pergunta original;
* resposta;
* autor da resposta;
* fonte;
* data, quando disponível;
* itens impactados;
* status.

Depois de registrar uma resposta:

1. atualize os requisitos relacionados;
2. atualize histórias;
3. atualize critérios de aceite;
4. atualize conflitos;
5. avalie se novas perguntas surgiram;
6. altere a pergunta para `resolved` somente depois da incorporação.

## Passo 10 — Formalizar requisitos funcionais

Cada requisito funcional deve:

* possuir um único comportamento principal;
* utilizar linguagem normativa;
* ser verificável;
* evitar detalhes técnicos;
* possuir fonte;
* indicar seu status;
* indicar perguntas relacionadas.

Formato recomendado:

`FR-001 — O sistema deve permitir que um usuário autorizado consulte
os títulos em aberto de uma empresa selecionada.`

Evite:

`FR-001 — Criar endpoint GET usando Spring Boot para consultar títulos.`

A segunda redação é uma decisão de implementação.

## Passo 11 — Formalizar regras de negócio

Cada regra deve:

* ser declarativa;
* possuir condição clara;
* evitar termos subjetivos;
* preservar fórmulas e limites exatamente como confirmados;
* registrar exceções;
* possuir fontes.

Exemplo:

`BR-002 — Um título deve ser classificado como vencido quando sua data
de vencimento for anterior à data de referência e seu saldo em aberto
for maior que zero.`

## Passo 12 — Formalizar requisitos de integração e dados

Requisitos de integração devem descrever necessidades e comportamentos
externamente observáveis, não componentes técnicos internos.

Registre, quando conhecido:

* sistema de origem;
* sistema de destino;
* evento ou operação;
* dados trocados;
* condição de sucesso;
* condição de falha;
* necessidade de reprocessamento;
* necessidade de rastreabilidade.

Requisitos de dados devem registrar:

* dado;
* origem;
* obrigatoriedade;
* validação;
* sensibilidade;
* retenção, quando confirmada;
* comportamento em caso de ausência ou inconsistência.

## Passo 13 — Formalizar requisitos não funcionais

Um requisito não funcional deve ser mensurável quando possível.

Categorias:

* desempenho;
* disponibilidade;
* segurança;
* privacidade;
* auditoria;
* escalabilidade;
* acessibilidade;
* observabilidade;
* compatibilidade;
* volume;
* conformidade.

Quando a necessidade existir, mas a métrica não estiver definida:

1. registre o requisito como candidato;
2. crie uma pergunta;
3. não invente um valor.

## Passo 14 — Criar histórias de usuário

Uma história deve estar ligada a requisitos já identificados.

Formato:

`Como <ator>, quero <capacidade>, para <benefício>.`

Uma história deve conter:

* identificador;
* título;
* status;
* ator;
* capacidade;
* benefício;
* requisitos relacionados;
* critérios de aceite;
* perguntas bloqueantes;
* fontes.

Não inclua:

* classes;
* arquivos;
* bibliotecas;
* controllers;
* migrations;
* estimativas;
* subtarefas técnicas.

## Passo 15 — Criar critérios de aceite

Crie critérios para os comportamentos confirmados.

Considere:

* cenário principal;
* erros;
* permissões;
* limites;
* ausência de dados;
* dados inválidos;
* duplicidade;
* falha de integração;
* processamento parcial;
* estado anterior e posterior.

Formato recomendado:

`AC-001`

`Dado que o usuário possui acesso à empresa selecionada`

`Quando consultar os títulos em aberto`

`Então o sistema deve apresentar somente os títulos com saldo maior
que zero dessa empresa.`

Não produza critérios para comportamentos ainda desconhecidos.

Associe o critério à pergunta bloqueante correspondente quando necessário.

## Passo 16 — Construir rastreabilidade

Todo requisito confirmado deve apontar para pelo menos uma fonte.

Toda história deve apontar para requisitos.

Todo critério de aceite deve apontar para uma história ou requisito.

Toda pergunta deve indicar os itens afetados.

Todo conflito deve indicar suas fontes e a pergunta de resolução.

A matriz deve permitir responder:

* De onde veio este requisito?
* Qual história o implementa?
* Qual critério o valida?
* Qual pergunta ainda pode alterá-lo?

## Passo 17 — Revisar consistência

Antes de salvar, verifique:

* requisitos duplicados;
* IDs duplicados;
* histórias sem ator ou valor;
* critérios não verificáveis;
* requisitos sem fonte;
* perguntas já respondidas;
* conflitos não registrados;
* hipóteses tratadas como fatos;
* detalhes técnicos indevidos;
* itens fora do escopo apresentados como requisitos;
* regras com termos vagos;
* divergências entre requisitos e critérios.

## Passo 18 — Calcular prontidão

Use `clarification-required` quando existir pelo menos uma pergunta
bloqueante aberta.

Use `ready-for-validation` quando:

* não houver bloqueios conhecidos;
* requisitos principais estiverem formalizados;
* histórias principais possuírem critérios verificáveis;
* fontes estiverem registradas;
* conflitos críticos estiverem resolvidos.

Use `validated` somente após aprovação explícita.

Defina `handoff_ready: true` somente quando:

* o status for `validated`;
* não existirem perguntas P0 abertas;
* não existirem conflitos críticos sem tratamento;
* requisitos confirmados possuírem fontes;
* histórias estiverem ligadas aos requisitos;
* critérios de aceite forem verificáveis.

# Atualização incremental

Ao incorporar novas fontes:

* preserve IDs;
* altere apenas itens impactados;
* não perca respostas anteriores;
* marque itens substituídos como `superseded`;
* registre novos conflitos;
* reabra perguntas quando a premissa da resposta tiver mudado;
* incremente a revisão;
* atualize o histórico.

# Economia de contexto

Não copie grandes trechos das fontes.

Utilize referências curtas.

Não repita a mesma informação em múltiplas seções.

Mantenha detalhes da reunião nos respectivos `meeting-analysis.md`.

No dossiê de requisitos, mantenha somente o contexto necessário para
entender e validar a demanda.

No chat, apresente apenas:

* mudanças;
* pendências;
* perguntas prioritárias;
* status;
* caminho do artefato.
