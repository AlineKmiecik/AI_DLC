---

name: technical-design
description: Metodologia para transformar uma tarefa de desenvolvimento aprovada em um plano técnico baseado no código real do repositório. Analisa arquitetura hexagonal, arquivos, contratos, dados, integrações, configurações, segurança, erros, observabilidade, testes e riscos. Produz desenhos por tarefa e diagramas PlantUML, sem alterar código.
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Objetivo

Produzir um plano técnico que permita implementar uma tarefa com:

* escopo controlado;
* aderência ao projeto;
* decisões explícitas;
* riscos conhecidos;
* rastreabilidade;
* estratégia de testes;
* instruções suficientes para o Coding Agent.

O plano deve explicar como a solução será implementada.

Ele não deve executar a implementação.

# Artefatos

Utilize:

`technical-design-template.md`

Produza:

```text
docs/ai-dlc/work-items/<work-item-id>/technical-design/
├── technical-design-index.md
├── <task-id>-technical-design.md
└── diagrams/
    └── <task-id>-*.puml
```

# Princípio central

Não desenhe a arquitetura que você gostaria que o projeto tivesse.

Desenhe a alteração que respeita a arquitetura que o projeto realmente
possui, salvo quando existir uma decisão aprovada para modificá-la.

# Processo de desenho

## Passo 1 — Selecionar uma tarefa

O trabalho deve começar por uma tarefa específica.

Identifique:

* task ID;
* categoria;
* história pai;
* objetivo;
* requisitos;
* critérios de aceite;
* dependências;
* sistemas;
* fora do escopo.

Não desenhe várias tarefas simultaneamente, salvo para criar ou atualizar
o índice.

## Passo 2 — Verificar elegibilidade

O desenho completo se aplica a:

* `BACKEND_DEVELOPMENT`;
* `BACKEND_REPOSITORY_SETUP`.

Para tarefas frontend, limite-se a contratos e dependências, salvo
solicitação explícita.

Para tarefas Xray, homologação e Confluence, não produza desenho interno.

## Passo 3 — Carregar somente o contexto necessário

Leia:

* a descrição completa da tarefa;
* a história pai;
* requisitos relacionados;
* critérios relacionados;
* fluxos relacionados;
* sistemas relacionados;
* decisões diretamente relacionadas.

Não carregue todas as reuniões nem todas as histórias da demanda quando
elas não forem necessárias.

# Passo 4 — Localizar instruções do projeto

Procure:

* `AGENTS.md`;
* `.github/copilot-instructions.md`;
* instruções específicas por diretório;
* ADRs;
* guias arquiteturais;
* README;
* arquivos de build;
* convenções de teste;
* documentação de execução.

Registre quais instruções foram utilizadas.

Quando duas instruções entrarem em conflito, crie uma pergunta.

# Passo 5 — Identificar o baseline do repositório

Registre, quando disponível:

* repositório;
* branch;
* commit;
* módulo;
* runtime;
* linguagem;
* framework;
* ferramenta de build;
* estratégia de testes;
* arquitetura observada.

Não invente branch, commit ou versões.

Quando não estiverem disponíveis, utilize:

`Não informado.`

# Passo 6 — Fazer reconhecimento do código

Localize referências para:

* fluxo semelhante;
* caso de uso semelhante;
* adapter de entrada;
* adapter de saída;
* persistência;
* integração;
* validação;
* tratamento de erro;
* configuração;
* testes;
* observabilidade.

Para cada referência, registre:

* caminho;
* símbolo;
* motivo da relevância;
* padrão que será reutilizado;
* limitações da comparação.

Prefira referências do mesmo módulo e contexto de negócio.

Não use um arquivo apenas porque possui nome parecido.

# Passo 7 — Descrever o comportamento atual

Quando for manutenção, descreva:

* ponto de entrada atual;
* fluxo atual;
* componentes envolvidos;
* comportamento atual;
* limitação ou defeito;
* testes existentes;
* integrações existentes.

Diferencie comportamento observado no código de comportamento esperado
pelos requisitos.

Quando for funcionalidade nova, registre:

`Não existe fluxo atual equivalente.`

# Passo 8 — Definir o comportamento técnico futuro

Descreva:

* ponto de entrada;
* coordenação da aplicação;
* regras de domínio;
* saídas;
* integrações;
* persistência;
* erros;
* observabilidade;
* resultado esperado.

Use linguagem técnica, mas não escreva implementação linha a linha.

# Passo 9 — Mapear a arquitetura hexagonal

Analise as seguintes áreas, quando aplicáveis.

## Domínio

Avalie:

* entidades;
* value objects;
* regras invariantes;
* serviços de domínio;
* eventos de domínio;
* exceções de domínio.

Uma regra de negócio não deve ser movida para controller, client ou
repositório por conveniência.

## Aplicação

Avalie:

* casos de uso;
* comandos e consultas;
* modelos de entrada e saída;
* coordenação do fluxo;
* boundaries transacionais;
* ports de entrada;
* ports de saída.

## Adapters de entrada

Avalie:

* controllers;
* consumers;
* listeners;
* jobs;
* schedulers;
* commands;
* mapeamento de entrada;
* validação de formato;
* autenticação e autorização.

## Adapters de saída

Avalie:

* persistência;
* clientes HTTP;
* mensageria;
* armazenamento;
* cache;
* serviços externos;
* mapeamento de saída;
* tradução de erros externos.

## Composição

Avalie:

* dependency injection;
* configuração;
* factories;
* módulos;
* inicialização;
* feature flags.

Utilize os nomes reais adotados pelo projeto.

# Passo 10 — Definir impacto em arquivos

Para cada arquivo, registre:

* operação;
* caminho;
* símbolo;
* responsabilidade;
* motivo;
* requisitos;
* risco;
* dependências.

Operações:

* `Create`;
* `Modify`;
* `Preserve`;
* `Remove`;
* `Candidate`.

Não produza uma lista genérica como:

```text
Controller
Use case
Repository
```

Utilize caminhos e símbolos sustentados pelo projeto.

Para arquivos novos, indique que o caminho é uma proposta.

# Passo 11 — Definir contratos de entrada

Quando houver API, consumer, evento ou job, registre:

* mecanismo de entrada;
* operação;
* autenticação;
* autorização;
* campos;
* validações de formato;
* idempotência;
* respostas;
* erros;
* compatibilidade.

Não altere comportamento funcional aprovado.

Quando um contrato ainda não estiver definido, crie uma pergunta.

# Passo 12 — Definir contratos de saída

Para cada port ou integração, registre:

* finalidade;
* consumidor ou provedor;
* dados enviados;
* dados recebidos;
* erros possíveis;
* timeout;
* retry;
* fallback;
* circuit breaker;
* idempotência;
* observabilidade.

Somente confirme timeout, retry e protocolo quando houver fonte.

Caso contrário, trate como proposta ou pergunta.

# Passo 13 — Dados e persistência

Avalie:

* entidades persistidas;
* tabelas;
* colunas;
* índices;
* constraints;
* consultas;
* migrations;
* compatibilidade;
* rollback;
* volume;
* retenção;
* dados sensíveis.

Diferencie:

* mudança obrigatória;
* mudança proposta;
* mudança não necessária.

Não crie migration nesta etapa.

# Passo 14 — Transação e concorrência

Avalie:

* início e fim da transação;
* consistência;
* concorrência;
* duplicidade;
* locking;
* idempotência;
* reprocessamento;
* processamento parcial;
* ordenação;
* compensação.

Não adicione mecanismos complexos sem necessidade demonstrada.

# Passo 15 — Segurança

Avalie:

* autenticação;
* autorização;
* exposição de dados;
* validação de entrada;
* logs sensíveis;
* secrets;
* controle por empresa ou tenant;
* ameaças relacionadas ao fluxo;
* dependências externas.

Não registre credenciais reais.

# Passo 16 — Configurações

Identifique:

* variáveis de ambiente;
* propriedades;
* feature flags;
* URLs externas;
* timeouts;
* retries;
* nomes de tópicos ou filas;
* credenciais referenciadas por secret;
* diferenças entre ambientes.

Para cada configuração nova, registre:

* nome proposto;
* finalidade;
* tipo;
* obrigatoriedade;
* valor padrão, quando aprovado;
* ambientes afetados;
* impacto de ausência;
* informação sensível ou não.

# Passo 17 — Tratamento de erros

Defina:

* erros de domínio;
* erros de validação;
* erros de autorização;
* erros de persistência;
* erros de integração;
* tradução entre erros internos e respostas externas;
* mensagens;
* códigos;
* logs;
* condições de retry.

Não exponha detalhes internos ou dados sensíveis.

# Passo 18 — Observabilidade

Avalie:

* logs;
* métricas;
* tracing;
* correlation ID;
* auditoria;
* alertas;
* dashboards;
* monitoramento de erros;
* identificação do fluxo.

Registre somente o necessário ao risco e ao padrão do projeto.

# Passo 19 — Compatibilidade

Avalie:

* consumidores existentes;
* contratos atuais;
* dados existentes;
* migrations;
* versionamento;
* implantação gradual;
* feature flag;
* rollback;
* coexistência entre versões.

Qualquer quebra de compatibilidade deve estar explícita.

# Passo 20 — Estratégia de testes automatizados

Defina testes relacionados à implementação.

## Unitários

Cobrir:

* regras novas;
* regras alteradas;
* limites;
* exceções;
* casos negativos.

## Integração

Cobrir, quando aplicável:

* persistência;
* clients;
* mensageria;
* serialização;
* configuração;
* framework.

## Contrato

Cobrir, quando aplicável:

* consumidores;
* provedores;
* OpenAPI;
* schemas;
* eventos.

## Arquitetura

Cobrir, quando o projeto adotar:

* dependências entre camadas;
* isolamento do domínio;
* convenções.

## Regressão

Identificar testes existentes que precisam continuar passando.

Não substitua testes Xray por testes automatizados.

Não crie testes Xray nesta etapa.

# Passo 21 — Comandos de validação

Registre somente comandos encontrados em fontes autorizadas.

Exemplos de categorias:

* build;
* unit tests;
* integration tests;
* lint;
* static analysis;
* architecture tests;
* contract tests.

Não invente comandos.

Quando não forem encontrados, crie uma pergunta ou registre a lacuna.

# Passo 22 — Sequência de implementação

Crie uma sequência de passos pequenos e verificáveis.

Exemplo:

```text
1. Ajustar o modelo de domínio.
2. Atualizar o port de saída.
3. Implementar o adapter externo.
4. Atualizar o caso de uso.
5. Adaptar o ponto de entrada.
6. Adicionar configurações.
7. Criar os testes.
8. Executar as verificações do projeto.
```

A ordem deve refletir dependências reais.

Não use essa seção para escrever código.

# Passo 23 — Diagramas PlantUML

## Sequência principal

Use para representar:

* ator;
* adapter de entrada;
* aplicação;
* domínio;
* ports;
* adapters de saída;
* sistemas externos;
* retorno.

Arquivo:

`<task-id>-sequence-main.puml`

## Componentes

Use para representar:

* módulos;
* fronteiras;
* ports;
* adapters;
* dependências;
* sistemas externos.

Arquivo:

`<task-id>-components.puml`

## Sequência de erro

Use quando um erro ou fallback for relevante.

Arquivo:

`<task-id>-sequence-error.puml`

## Estados

Use quando existir ciclo de vida ou transição de status.

Arquivo:

`<task-id>-state.puml`

## Dados

Use quando houver mudança relevante em entidades ou persistência.

Arquivo:

`<task-id>-data-model.puml`

## Deployment

Use quando houver novo serviço, repositório ou infraestrutura.

Arquivo:

`<task-id>-deployment.puml`

Cada diagrama deve registrar os requisitos representados.

# Passo 24 — Decisões técnicas

Para cada decisão, registre:

* ID;
* contexto;
* decisão;
* alternativas;
* justificativa;
* consequências;
* responsável;
* status.

Status:

* `Proposed`;
* `Approved`;
* `Rejected`;
* `Superseded`.

Não transforme recomendação em decisão aprovada.

# Passo 25 — Riscos

Avalie:

* regressão;
* integração;
* dados;
* segurança;
* desempenho;
* concorrência;
* compatibilidade;
* implantação;
* observabilidade;
* dependência externa;
* ausência de testes;
* ambiguidade.

Para cada risco, registre:

* probabilidade;
* impacto;
* mitigação;
* evidência;
* responsável.

# Passo 26 — Criar o contrato para o Coding Agent

O contrato deve conter:

* tarefa;
* objetivo;
* arquivos permitidos;
* arquivos proibidos;
* alterações esperadas;
* decisões aprovadas;
* testes obrigatórios;
* comandos obrigatórios;
* diagramas relevantes;
* fora do escopo;
* condições de parada;
* evidências esperadas.

Condições de parada podem incluir:

* requisito funcional ausente;
* conflito entre baselines;
* contrato externo desconhecido;
* migration destrutiva sem aprovação;
* mudança fora do escopo;
* falha não relacionada nos testes;
* necessidade de nova dependência não aprovada.

# Novo repositório

Para `BACKEND_REPOSITORY_SETUP`, avalie:

* repositório ou template de referência;
* nome;
* finalidade;
* linguagem;
* runtime;
* build;
* estrutura inicial;
* arquitetura;
* package base;
* políticas;
* permissões;
* pipeline;
* testes;
* análise estática;
* segurança;
* health checks;
* observabilidade;
* configuração;
* secrets;
* deployment;
* ownership;
* README inicial.

Não crie o repositório.

Não invente padrões organizacionais não fornecidos.

# Atualização incremental

Quando houver ajuste:

1. preserve IDs;
2. altere somente seções impactadas;
3. atualize diagramas relacionados;
4. atualize o contrato do Coding Agent;
5. atualize riscos e perguntas;
6. incremente a revisão;
7. registre o histórico.

# Verificação final

Antes de marcar como pronto, confirme:

* tarefa e categoria corretas;
* baselines registradas;
* instruções do repositório lidas;
* código semelhante pesquisado;
* referências existentes possuem caminhos;
* itens propostos estão identificados;
* arquivos impactados estão listados;
* arquitetura do projeto foi respeitada;
* contratos estão definidos;
* dados e integrações foram avaliados;
* erros e segurança foram avaliados;
* configurações foram avaliadas;
* estratégia de testes está definida;
* comandos estão sustentados por fontes;
* sequência de implementação está definida;
* diagramas aplicáveis existem;
* perguntas bloqueantes foram resolvidas;
* riscos críticos possuem tratamento;
* contrato do Coding Agent está completo;
* não houve alteração de código.

# Economia de contexto

Crie um desenho por tarefa.

Não copie integralmente:

* transcrições;
* requisitos;
* task plan;
* modelo macro;
* código.

Utilize:

* IDs;
* caminhos;
* símbolos;
* referências curtas.

No handoff, o Coding Agent deve receber somente:

* descrição da tarefa;
* desenho técnico daquela tarefa;
* arquivos relevantes;
* instruções do repositório.
